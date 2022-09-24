<template>
    <div class="main">
        <cards />
        <cards />
        <cards />
        <cards />
        <cards />
        <cards />
    </div>
</template>

<script>
import feedTable from "~/components/tables/feedTable.vue";
export default {
    components: { feedTable },
    head() {
        return {
            title: "Home",
            meta: [
                {
                    hid: "description",
                    name: "descrioption",
                    content: "just about the home page",
                },
            ],
        };
    },
};
</script>

<style lang="scss">
.main {
    display: flex;
    justify-content: space-evenly;
    flex-wrap: wrap;
}
@media only screen and (min-width: 1024px) {
    .main {
        justify-content: flex-start;
    }
}
</style>
