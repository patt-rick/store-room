<template>
    <div class="parent">
        <div class="header"><appheader /></div>
        <div class="routes">
            <Nuxt />
        </div>
        <div class="navigations"><appnav /></div>
    </div>
</template>
<style lang="scss" scoped>
.parent {
    display: grid;
    grid-template-columns: 100%;
    grid-template-rows: 60px calc(100vh - 110px) 50px;
    background-color: #fff;
}

.routes {
    padding: 5px;
    background-color: #efefef;
    overflow: scroll;
    overflow-x: hidden;
    scrollbar-width: none;
    -ms-overflow-style: none;
}
.routes::-webkit-scrollbar {
    display: none;
}

@media only screen and (min-width: 720px) {
    .parent {
        display: grid;
        grid-template-columns: 67px calc(100% - 67px);
        grid-template-rows: 60px calc(100vh - 60px);
    }
    .header {
        grid-area: 1 / 2 / 2 / 3;
    }
    .routes {
        grid-area: 2 / 2 / 3 / 3;
        scrollbar-width: 20px;
        -ms-overflow-style: none;
    }

    .navigations {
        grid-area: 1 / 1 / 3 / 2;
    }
}
@media only screen and (min-width: 1024px) {
    .parent {
        grid-template-columns: 220px calc(100% - 220px);
    }
}
</style>
