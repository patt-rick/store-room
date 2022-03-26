<template>
  <div class="main">
      <feed-table/>
    <cards />
    <cards />
    <cards />
    <create-modal @feedback="popfeedback1" />
    <logout-modal></logout-modal>
    <delete-modal @feedback="popfeedback2"/>
    <notice :message="feedbackMessage" v-show="show" ></notice>
  </div>
</template>

<script>
import feedTable from '~/components/tables/feedTable.vue';
export default {
  components: { feedTable },
   head(){
        return{
            title: "Dashboard",
            meta: [
                {
                    hid: "description",
                    name: "description",
                    content: "just about the dashboard "
                    
                }
            ]
        };
    },
    data(){
        return{
            show: false,
            feedbackMessage: 'success',
        }
    }, methods:{
        popfeedback1(){
            this.feedbackMessage = 'Item created succesfully'
            this.show = true;
            setTimeout(()=>{
                this.show = false;
            },1500)
        },
        popfeedback2(){
            this.feedbackMessage = 'Item deleted succesfully'
            this.show = true;
            setTimeout(()=>{
                this.show = false;
            },1500)
        }

    }
}
</script>

<style>
.main{
  display: flex;
  justify-content: flex-start;
  flex-wrap: wrap;
}
</style>