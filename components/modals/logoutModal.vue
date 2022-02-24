<template>
  <div v-show="this.show" class="modal">
      <div class="content">
          <div class="icon"></div>
          <div class="message"> Are you sure you want to log out ?</div>
          <div class="btn">
            <button @click="logout()" class="confirm">LOG OUT</button>
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
        logout(){
            this.show = !this.show;
            // perform the tast at hand eg. logout
        }
    }

}
</script>

