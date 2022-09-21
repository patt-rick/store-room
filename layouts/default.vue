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
.header {
    border: 1px solid red;
}
.routes {
    border: 1px solid red;
}
.navigations {
    border: 1px solid red;
}

@media only screen and (min-width: 720px) {
    .parent {
        display: grid;
        grid-template-columns: 67px calc(100% - 67px);
        grid-template-rows: 60px calc(100vh - 60px);
    }
    .header {
        grid-area: 1 / 2 / 2 / 3;
        border: 1px solid red;
    }
    .routes {
        grid-area: 2 / 2 / 3 / 3;
        border: 1px solid red;
    }
    .navigations {
        grid-area: 1 / 1 / 3 / 2;
        border: 1px solid red;
    }
}
@media only screen and (min-width: 1024px) {
    .parent {
        grid-template-columns: 200px calc(100% - 200px);
    }
}
</style>
