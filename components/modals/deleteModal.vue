<template>
  <div v-show="this.show" class="modal">
      <div class="content">
          <div class="icon"></div>
          <div class="message"> Select Delete to delete this item from your inventory. </div>
          <div class="btn">
            <button @click="del()" class="confirm">DELETE</button>
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
        del(){
            this.show = !this.show;
            this.$emit('feedback')
            // perform the tast at hand eg. logout
        }
    }

}
</script>
