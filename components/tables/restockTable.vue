<template>
  <div>
      <div class="restock-table">
          <span class="heading">RESTOCK</span>
          <div class="not-scroll">
          <div v-for="tx in txt" :key="tx.message" class="restock-item">
              <div class="img"><img width="40" height="40" src="" alt=""></div>
              <span>ipsum dolor  {{tx.message}}.</span>
              <div v-if="tx.value < 15" class="color-indicator-red"></div>
              <div v-else class="color-indicator-green"></div>
          </div>
          </div>
      </div>
  </div>
</template>

<script>
export default {
    data(){
        return{
            txt:[{message: 'one',value: 10},{message: 'crime',value: 43},{message: 'three',value: 3},{message: 'four',value: 43},{message: 'five',value: 43},{message: 'six',value: 43},{message: 'one',value: 43},{message: 'crime',value: 43},{message: 'three',value: 43},{message: 'four',value: 43},{message: 'five',value: 43},{message: 'six',value: 43}]
        }
    }

}
</script>

<style lang="scss">
.not-scroll{
    max-height: 300px;
    overflow: scroll;
    width: 260px;
    // -ms-overflow-style: none;
    // scrollbar-width: none;
}
.not-scroll::-webkit-scrollbar{
    width: 3px;
}

.color-indicator-green{
    height: 0px;
    width: 0px;
    border: 6px solid transparent;
    border-bottom-color: green;
}
.color-indicator-red{
    height: 0px;
    width: 0px;
    border: 6px solid transparent;
    border-top-color: red;
}
.restock-table{
    min-width: 235px;
    max-width: 300px;
    background-color: #fff;
    // border: 1px solid #ccc;
    border-radius: 10px;
    box-shadow: 1px 1px 4px rgba(#000,0.2);

    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: center;

    .heading{
        width: 100%;
        border-bottom: 3px solid #efefef;
        text-align: center;
        padding: 10px 0px;
    }
    .restock-item{
        width: 90%;
        display: flex;
        justify-content: space-between;
        align-items: center;
        min-height: 40px;
        padding: 6px;
        border-bottom: 1px solid #ccc;

        .img{
            padding: 5px;
        }
        span{
            padding: 3px 5px;
        }
    }
}

</style>