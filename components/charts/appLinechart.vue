<template>
    <div class="main">
        <div class="drugLineChart">
            <canvas :key="componentKey" id="lineChart"></canvas>
        </div>
        <div class="box">
            <select name="" id="timez"  v-model="timeRange">
                <option value="hourly">Hourly</option>
                <option value="Daily">Daily</option>
                <option value="weekly" selected>Weekly</option>
                <option value="monthly" >Monthly</option>
            </select>
            <input type="number" name="" min="1"  max="20" id="numRange" v-model="number">
            <button class="view" @click="range()">view graph</button>
        </div>
    </div>
</template>

<script>
import axios from 'axios'
export default {
    data(){
        return {
            data: [],
            drugName: null,
            labels : [],
            componentKey: 0,
            number : 1,
            timeRange: "monthly"
        }
    },
    mounted(){
        this.chartIt()
    },
     methods: {
         range() {
            this.componentKey += 1;
            this.chartIt()
         },
        async getData() {
            const response = await axios.get('single_drug_sale.json',{
                                    params: {
                                        time: this.timeRange,
                                        number: this.number
                                    }
                                });
            
            response.data.forEach(drug => {
                this.drugName = drug.drug_name;
                this.data = drug.sold;
                this.labels = drug.label;
            });
        },
        async chartIt(){
            await this.getData();
            new Chart("lineChart", {
                type: "line",
                data: {
                    labels: this.labels,
                    datasets: [{
                        data : this.data,
                        label: this.drugName,
                        borderColor: 'red',
                        backgroundColor: 'red',
                        pointRadius: 1,
                        hitRadius: 10,
                        pointHoverBackgroundColor: 'white',
                        tension: 0,
                        borderWidth: 2
                        
                    }]
                },
                options: {
                    maintainAspectRatio: false,
                    layout: {
                        padding: 20
                    },
                    responsive: true,
                    plugins: {
                        tooltip: {
                            displayColors: false,
                            callbacks: {
                                title: function(item){
                                    return  item[0].dataset.label ;
                                    
                                },
                                label: function(item){
                                    return 'Total units sold on '+item.label +': ' +item.raw ;
                                    
                                },
                            }
                        },
                        legend: {
                            display: true,
                            position: 'top',
                            labels: {
                                color: '#000',
                                boxWidth: 16
                            }
                        },
                        title: {
                            display: false,
                            text: 'Drug cycle',
                            color: '#000',
                        }
                    },
                    scales: {
                        y: {
                            beginAtZero: true,
                        },
                        x: {
                        },
                    }
                }
            });
        }
    }
}
</script>

<style scoped>
.main{
    background-color: #fff;
    height: 350px;
    width: 550px;
    margin: auto;
    margin-bottom: 50px;
    border-radius: 5px;
    box-shadow: 2px 3px 20px 6px rgba(0,0,0,0.4);
    display: flex;
    flex-direction: column;
}
.drugLineChart{
    height: 300px;
    width: 500px;
}
.box{
    width: 400px;
    margin-bottom: 20px;
    color: #777;
    display: flex;
    justify-content: space-evenly;
    font-family:Verdana, Geneva, Tahoma, sans-serif;
}
.box select {
    color: #777;
    border: none;
    border-bottom: 1px solid #bbb;
    padding: 8px;
    width: 180px;
    font-size: 20px;
    -webkit-appearance: button;
    -moz-appearance: button;
    -o-appearance: button;
    -ms-appearance: button;
    appearance: button;
    outline: none;
  }
.box input[type=number] {
    width: 40px;
    color: #777;
    outline: none;
    padding: 10px;
    border: 1px solid #ccc;
    font-family:Verdana, Geneva, Tahoma, sans-serif;
}
.view{
  font-size: 16px;
  padding: 10px;
  border: 1px solid #bbb;
  color:#777;
  background-color: #fff;
  outline: none;
}
.view:hover{
  background-color: rgba(0,0,0,0.1)
}
</style>