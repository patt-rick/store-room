<template>
  <div class="m">
      <div class="wrap">
          <div class="quantity-data">
              <div class="quantity">
                  <strong class="num">{{item}}</strong> <span>LEFT</span>
              </div>
              <div>
                    <div  class="restock-date">
                        <span>Last Restock</span>
                        <div class="date">{{restockDate}}</div>
                    </div>
                </div>
          </div>
          <div class="brand-name">
              <div class="name">
                  <span>Shoes</span>
                  <span class="brand">GUCCI</span>
              </div>
              <img src="../assets/arts-collectibles.jpg" loading="lazy" alt="" >
          </div>
      </div>
  </div>
</template>

<script>
export default {
    data(){
        return {
            item: 17,
            restockDate:'14-09-2012'
        }
    }
}
</script>

<style lang="scss">
    $primary-color: #5C415D;
    $accent-color: #ffcba4;
    $grey: #ccc;
    .m{
        display: inline-block;
        margin: 10px;
    }
    .wrap{
        height: 200px;
        width: 150px;
        background-color: #fff;
        border: 0px solid $grey;
        border-radius: 10px;
        padding: 7px;
        box-shadow: 0.5px 2px 4px rgba(#000,0.2);
        font-family: sans-serif;

        display: flex;
        align-items: center;
        justify-content: space-evenly;
        flex-direction: column;

        .quantity-data{
            height: 110px;
            width: 125px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            border-bottom: 1px solid #ccc;

            .quantity{
                display: flex;
                justify-content: space-between;
                align-items: flex-start;
                height: 75px;

                span{
                    padding: 10px;
                    color: #888;
                }
            }
            .num{
                padding: 0;
                font-size: 3.6em;
                font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
                color: $primary-color ;
            }
        }
        .restock-date{
            float: right;
            font-size: 0.7em;
            color:#888;
            .date{
                color:#333;
            }
        }

        .brand-name{
            display: flex;
            width: 125px;
            justify-content: space-between;

            img{
                width: 40px;
                height: 40px;
            }

            .name{
                display: flex;
                flex-direction: column;
                color: $accent-color;

                span{
                    font-size: 0.7em;
                    padding: 1px;
                }
                .brand{
                    font-weight: bold;
                    font-size: 1em;
                    color: $primary-color;
                }
            }
        }
    }
    @media only screen and (max-width: 775px){
        .wrap{
            height: calc((70/100) * 200px);
            width: calc((70/100) * 150px);
            padding: 4px;

            .quantity-data{
            height: calc((60/100) * 110px);
            width: calc((60/100) * 125px);

            .quantity{
                display: flex;
                justify-content: space-between;
                align-items: flex-start;
                height: 55px;

                span{
                    padding: 6px;
                    color: #888;
                    font-size: 0.8em;
                }
            }
            .num{
                padding: 0;
                font-size: calc((60/100) * 3.5em);
            }
        }
        .restock-date{
            float: right;
            font-size: 0.6em;
        }

        .brand-name{
            display: flex;
            width: calc((60/100) * 125px);
            justify-content: space-between;

            img{
                width: 30px;
                height: 30px;
            }
            .name{
                display: flex;
                flex-direction: column;

                span{
                    font-size: 0.5em;
                    padding: 1px;
                }
                .brand{
                    font-weight: bold;
                    font-size: 0.7em;
                }
            }
        }
    }
    }
</style>