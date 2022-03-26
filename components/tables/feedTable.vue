<template>
  <div>
      <div class="feed-table">
          <span class="heading">FEED</span>
          <div v-for="tx in txt" :key="tx.message" class="feed-item">
              <div class="img"><img width="40" height="40" src="@/assets/arts-collectibles.jpg" alt=""></div>
              <span>ipsum dolor sit amet consectetur {{tx.message}}.</span>
          </div>
      </div>
  </div>
</template>

<script>
export default {
    data(){
        return{
            txt:[{message: 'one'},{message: 'the sun shall soon shine in the west and therefore you ought to fight against crime'},{message: 'three'},{message: 'four'},{message: 'five'},{message: 'six'}]
        }
    }

}
</script>

<style lang="scss">
.feed-table{
    min-width: 235px;
    max-width: 250px;
    // border: 1px solid #ccc;
    border-radius: 10px;
    background-color: #fff;
    box-shadow: 0.5px 0.5px 4px rgba(#000,0.2);

    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: center;

    .heading{
        width: 100%;
        border-bottom: 1px solid #ccc;
        text-align: center;
        padding: 10px 0px;
    }
    .feed-item{
        display: flex;
        justify-content: center;
        align-items: center;
        min-height: 70px;
        padding: 6px;
        border-bottom: 1px solid #ccc;

        .img{
            flex:2;
            padding: 10px;
        }
        span{
            flex: 8;
            padding: 5px 10px;
        }
    }
}
 @media only screen and (min-width: 600px) {
     .feed-table{
    min-width: 235px;
    max-width: 350px;
     }
 }

</style>