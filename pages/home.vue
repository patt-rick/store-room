<template>
    <div class="home-grid-template">
        <div class="card-info">
            <cards/>
            <cards/>
            <cards/>
            <cards/>
            <cards/>
        </div>
        <feed-table class="span2"/>
    </div>
</template>

<script>
import feedTable from '~/components/tables/feedTable.vue';
export default {
  components: { feedTable },
    head(){
        return{
            title: "Home",
            meta: [
                {
                    hid: "description",
                    name: "descrioption",
                    content: "just about the home page"
                    
                }
            ]
        };
    }
};
</script>

<style lang='scss'>
    .home-grid-template{
        display: grid;
        gap: 1rem;
        padding-block: 1rem;
        margin-inline: auto;
        grid-template-areas: 
        'one one'
        // 'one one'
        'two two'
        'two two'
        'two two';

        .card-info{
            grid-area: one;
        //     display: flex;
        //     flex-wrap: wrap;
        //     justify-content: space-evenly;
        //     align-items: center;
            overflow-x: auto;
            overflow-y: hidden;
            white-space: nowrap;
        }


        .span2{
            grid-area: two;
            margin: auto;
        }
        
    }
    @media only screen and (min-width: 508px) {
        .home-grid-template{
        display: grid;
        grid-template-areas: 
        'one one one one'
        'three three two two '
        'three three two two ';
        }
    }
      @media only screen and (min-width: 600px) {
        .home-grid-template{
        display: grid;
        grid-template-areas: 
        'one one'
        // 'one one'
        'two two'
        'two two'
        'two two';
        }
    }
      @media only screen and (min-width: 963px) {
        .home-grid-template{
        display: grid;
        grid-template-areas: 
        'one one one one'
        'three three two two '
        'three three two two ';
        }
        
    }


</style>