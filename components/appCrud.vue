<template>
  <div>
      <div class="crud-wrap">
          <div class="crud-add">
              <button>add</button>
          </div>
          <div class="crud-edit">
              <button>edit</button>
          </div>
          <div class="crud-delete">
              <button class="del">delete</button>
          </div>
          <span>ITEM</span>
      </div>
  </div>
</template>

<script>
export default {

}
</script>

<style lang="scss">
    $primary-color: #5C415D;
    $accent-color: #ffcba4;
    .crud-wrap{
        background-color: #fff;
        max-width: 250px;
        height: 50px;
        // border: 1px solid #ccc;
        border-radius: 6px;
        box-shadow: 1px 2px 4px rgba(#000, 0.3);

        display: flex;
        justify-content: space-evenly;
        align-items: center;

        button{
            background-color: $primary-color;
            border: 1px solid $primary-color;
            border-radius: 4px;
            color: $accent-color;
            text-transform: uppercase;
            font-size: 12px;
            letter-spacing: 0.1em;
            padding: 6px;
            cursor: pointer;

            &:hover{
                background-color: rgba($primary-color,0.9);
            }
        }
         .del{
            background: red;
            border: red;

            &:hover{
                background-color: rgba(red,0.9);
            }
        }
        span{
         font-weight: 700;
         color: #444;
         font-size: 12px;
         letter-spacing: 0.1em;
        }
    }
   
</style>