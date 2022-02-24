<template>
<div class="add-item-modal">
   <div class="add-form">
            <form @submit.prevent="addItem"  class="login-form">
                <input class="input" v-model="name" type="text" placeholder="name" required />
                <div ><input class="input" v-model="type" type="text" placeholder="type" required /></div>
                <input class="half-num"  v-model="quantity" type="number" placeholder="item quantity" required />
                <label for="color">color</label><input type="color" class="half-col" name="color" v-model="color">
                <div class="end">
                <input type="submit" value="add item"><input @click="close" type="button" value="cancel">
                </div>
            </form>  
        </div>
</div>    
</template>

<script>
export default {
    data(){
        return{
            name: '',
            type: '',
            quantity: null,
            color: '#000000'
        
        }
    },
    methods:{
        addItem(){
            this.$emit('closeit')
            const item ={
                name: this.name,
                type: this.type,
                quantity: this.quantity,
                color: this.color
            }
            console.log(item)
        },
        close(){
            this.$emit('closeit')
        }
    }

}
</script>

<style lang="scss">
$primary-color: #5C415D;
.add-item-modal{
    position: fixed;
    top: 0;
    right: 0;
    left: 0;
    bottom: 0;
    background-color: rgba(#000,0.2);
    z-index: 101;
    display: flex;
    justify-content: center;
    align-items: center;
}
    .add-form{
        width: 250px;
        background-color: rgba(#fff,0.9);
        padding: 20px 10px;
        border-radius: 6px;

        .end{
            display: flex;
            justify-content: space-evenly;
            margin-top: 25px;
        }
        .input {
            outline: 0;
            background: #f2f2f2;
            width: 100%;
            border: 0;
            border-radius: 5px;
            margin: 0 0 15px;
            padding: 10px;
            box-sizing: border-box;
            font-size: 12px;
            font-family: 'Comfortaa', cursive;

        }
         .half-num {
            outline: 0;
            background: #f2f2f2;
            width: 60%;
            border: 0;
            border-radius: 5px;
            padding: 10px;
            margin: 0 0 10px;
            box-sizing: border-box;
            font-size: 12px;
            font-family: 'Comfortaa', cursive;

        }
        .half-col {
            outline: 0;
            background: transparent;
            width: 40px;
            height: 40px;
            border: 0;
            margin: 0 0 10px;
            box-sizing: border-box;
            position: relative;
            top: 8px;
            left: 15px;

        }
        .input:focus {
            background: #dbdbdb;
        }
        input[type=submit],input[type=button] {
            font-family: 'Comfortaa', cursive;
            text-transform: uppercase;
            outline: 0;
            background: $primary-color;
            width: 40%;
            border: 0;
            border-radius: 5px;
            padding: 10px 15px;
            color: #FFFFFF;
            font-size: 10px;
            -webkit-transition: all 0.3 ease;
            transition: all 0.3 ease;
            cursor: pointer;
        }
        input[type=submit]:hover{
        background-color: rgba($primary-color, 0.9);
        }

        input[type=submit]:active {
        background: $primary-color;
        }
    
    }
</style>