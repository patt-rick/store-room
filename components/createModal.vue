<template>
  <div v-show="this.show" class="modal">
      <div class="content">
          <div class="icon"></div>
          <div class="message"> Select Create to add this item to your inventory. </div>
          <div class="btn">
            <button @click="create()" class="confirm">CREATE</button>
            <button @click="cancel()" class="cancel">CANCEL</button>
          </div>
          
      </div>
  </div>
</template>

<script>
export default {
    data(){
        return {
            show: true,
        }
    },
    methods:{
        cancel(){
            this.show = !this.show;
        },
        create(){
            this.show = !this.show;

            this.$emit('feedback')
            // perform the tast at hand eg. logout
        }
    }

}
</script>

<style lang="scss">
$primary-color: #5C415D;
$accent-color: #ffcba4;

    .modal{
        position: fixed;
        top: 0;
        left: 0;
        bottom: 0;
        right: 0;
        background-color: rgba(#000,0.3);
        z-index: 99;
        display: flex;
        justify-content: center;
        align-items: center;

        .content{
            width: 60vw;
            max-width: 400px;
            height: 40vh;
            max-height: 400px;
            background-color: #fff;
            padding: 15px;
            border-radius: 12px;
            box-shadow: 1px 1px 10px rgba(#000,0.3);

            display: flex;
            justify-content: space-around;
            align-items: center;
            flex-direction: column;
        }

        .message{
            padding: 20px;
            font-size: 1.4em;
            text-align: center;
        }
        button{
            padding: 10px;
            margin: 0px 16px;
            border-radius: 6px;
            cursor: pointer;
            background-color: $primary-color ;
            border: 1px solid $primary-color;
            color: $accent-color;
            font-weight: 400;
            letter-spacing: 0.2em;
            box-shadow: 1px 1px 4px rgba(#000,0.2);
            transition: 0.43 ease-in;
            &:hover{
                background-color: rgba($color: $primary-color, $alpha: 0.9);
            }
        }
    }
    @media only screen and (max-width: 700px){
        .modal{
       
        .content{
            width: 70vw;
            height: 40vh;
            background-color: #fff;
            padding: 15px;
            border-radius: 12px;
            box-shadow: 1px 1px 10px rgba(#000,0.3);

            display: flex;
            justify-content: space-around;
            align-items: center;
            flex-direction: column;
        }

        .message{
            padding: 15px;
            font-size: 1.2em;
            text-align: center;
        }
        button{
            padding: 7px;
            margin: 0px 12px;
            margin-bottom: 5px;
            border-radius: 6px;
            cursor: pointer;
            font-weight: 400;
            letter-spacing: 0.1em;
            box-shadow: 1px 1px 4px rgba(#000,0.2);
            transition: 0.43 ease-in;
            &:hover{
                background-color: rgba($color: $primary-color, $alpha: 0.9);
            }
        }
    }
    }
</style>