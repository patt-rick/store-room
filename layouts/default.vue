<template>
<div class="parent">
  <div class="routes">
    <Nuxt />
  </div>
  <div class="header"><appheader/></div>
  <!-- <div class="footer">footer </div> -->
  <div class="navigations"><appnav/></div>
</div>
</template>
<style lang="scss" scoped>
*{
  box-sizing: border-box;
  margin: 0px;
  padding: 0px;
}
.header{
  height: 45px;
  width: 100%;
  position: fixed;
  top: 0;
  left: 0;
  right:0;
  background-color: #fff;
  // box-shadow: 0px 1px 4px rgba(#000,0.2);

}
.navigations{
  width: 100%;
  // margin-left: 2.5%;
  height: 55px;
  // border-radius: 20px;
  // margin-bottom: 10px;
  position: fixed;
  bottom: 0;
  left:0;
  right: 0;
  background-color: $primary-color;
  // box-shadow: 3px 3px 6px rgba(#000,0.3),
  // -3px -3px 6px rgba(#000,0.3);
}
.routes{
  padding-top: 45px;
  margin-bottom: 60px;
  background-color: #efefef;
}
// .footer{
//   background-color: cyan;
//   display: none;
//   box-shadow: 0px -1px 4px rgba(#000,0.2);
// }

@media only screen and (min-width: 600px){
  .header{
    height: 50px;
    margin-left: 200px;
    right: 0;
    width: calc(100% - 200px);
  }
  .navigations{
    height: 100vh;
    width: 200px;
    border-radius: 0px;
    margin-bottom: 0px;
    margin-left: 0px;
    top:0;
  }
  // .footer{
  //   display: block;
  //   position: fixed;
  //   bottom: 0;
  //   right: 0;
  //   width: calc(100% - 200px);
  //   height: 35px;
  // }
  .routes{
    padding-top: 70px;
    padding-left: 200px;
  }
}
@media only screen and (min-width: 840px){
  .navigations{
    width: 250px;
  }
  .footer, .header{
    width: calc(100% - 250px);
    right: 0;
    margin-left: 250px;
  }
  .routes{
    padding-left: 250px;
  }
}


</style>