<template>
  <div class="wrapp">
      <div class="mainn">
          <span>{{ message }}</span>
      </div>
  </div>
</template>

<script>
export default {
    props:['message'],
    data(){
        return{
            
        }
    },
    methods:{

    }
}
</script>

<style lang="scss">
.wrapp{
    display: flex;
    justify-content: center;
    align-items: center;
    // position: fixed;
    // top: 0;
    // bottom: 0;
    // left: 0;
    // right: 0;
    background-color: rgba(#000,0.3);
    z-index: 100;
}    
.mainn{
        width: 80vw;
        max-width: 250px;
        height: 80px;
        position: fixed;
        top: 120px;
        margin: auto;
        border-radius: 5px;
        background-color: #fff;
        color: #777;
        font-size: 1.3em;
        letter-spacing: 0.05em;
        font-family: sans-serif;
        display: flex;
        justify-content: center;
        align-items: center;
        text-align: center;
        box-shadow: 1px 1px 40px rgba(#000,0.3);
        transition: all 1s ease-in-out;
}
.mainn>span{
    position: relative;
    left: -20px;
    width: 90%;
}
.mainn >span:after{
    content:'';
    display: inline-block;
    font-size: 2.5em;
    color: #aaa;
    position: absolute;
    // right: 2px;
    // bottom: -4px;
}

    @media only screen and (max-width: 360px){
         .mainn{
             font-size: 1.1em;
         }
         .mainn >span:after{
            content:'';
            font-size: 2.5em;
            color: #aaa;
            position: absolute;
            // right: 0px;
            // bottom: -4px;
        }
     }
    @media only screen and (min-width: 672px){
        .mainn{
            min-width: 340px;
            height: 60px;
            position: fixed;
            right: 120px;
            top: 100px;
        }
    }
</style>