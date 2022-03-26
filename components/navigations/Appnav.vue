<template>
<div>
    <div class="company">
        <h2> Logo</h2>
    </div>
    <div class="appnav-wrap">
        <span @click="dashboardA" class="link">
            <nuxt-link :class="{'active' : dashboardActive}"  active to="/">
                <i v-if="!dashboardActive"><img src="@/assets/icons/normal/dashboard_32.png" alt=""></i>
                <i v-else><img src="@/assets/icons/hover/dashboard_32.png" alt=""></i>
                <span class="name">Dashboard</span>
            </nuxt-link>
        </span>
        <span @click="homeA" class="link">
            <nuxt-link :class="{'active' : homeActive}"  to="/home">
                <i v-if="!homeActive"><img src="@/assets/icons/normal/home_32.png" alt=""></i>
                <i v-else><img src="@/assets/icons/hover/home_32.png" alt=""></i>
                <span class="name">Home</span>
            </nuxt-link>
        </span>
        <span @click="inventoryA" class="link">
            <nuxt-link :class="{'active' : inventoryActive}"  to="/inventory">
                <i v-if="!inventoryActive"><img src="@/assets/icons/normal/inventory_32.png" alt=""></i>
                <i v-else><img src="@/assets/icons/hover/inventory_32.png" alt=""></i>
                <span class="name">Inventory</span>
            </nuxt-link>
        </span>
        <span @click="restockA" class="link">
            <nuxt-link :class="{'active' : restockActive}"  to="/restock">
                <i v-if="!restockActive"><img src="@/assets/icons/normal/restock_32.png" alt=""></i>
                <i v-else><img src="@/assets/icons/hover/restock_32.png" alt=""></i>
                <span class="name">Restock</span>
            </nuxt-link>
        </span>
        <span @click="historyA" class="link">
            <nuxt-link :class="{'active' : historyActive}"  to="/history">
                <i v-if="!historyActive"><img src="@/assets/icons/normal/history_32.png" alt=""></i>
                <i v-else><img src="@/assets/icons/hover/history_32.png" alt=""></i>
                <span class="name">History</span>
            </nuxt-link>
        </span>
    </div>
    <div class="logout">
        <nuxt-link class="log" to="/login">
            <i><img src="@/assets/icons/normal/logout_32.png" alt=""></i>
            <span>Logout</span>
        </nuxt-link>
    </div>
</div>
</template>
<script>
export default {
    data(){
        return{
            dashboardActive: true,
            historyActive: false,
            restockActive: false,
            homeActive: false,
            inventoryActive: false,
        }
    },
    methods:{
        homeA(){
            this.historyActive = false
            this.homeActive = true
            this.inventoryActive = false
            this.restockActive = false
            this.dashboardActive = false
        },
        inventoryA(){
            this.historyActive = false
            this.homeActive = false
            this.inventoryActive = true
            this.restockActive = false
            this.dashboardActive = false
        },
        restockA(){
            this.historyActive = false
            this.homeActive = false
            this.inventoryActive = false
            this.restockActive = true
            this.dashboardActive = false
        },
        dashboardA(){
            this.historyActive = false
            this.homeActive = false
            this.inventoryActive = false
            this.restockActive = false
            this.dashboardActive = true
        },
        historyA(){
            this.historyActive = true
            this.homeActive = false
            this.inventoryActive = false
            this.restockActive = false
            this.dashboardActive = false
        },
    }
}
</script>
<style lang="scss">
.company, .logout{
    display: none;
}
.active{
    .link a{
        border-color: $accent-color;
    }
    .name{
        color: $accent-color;
    }
}

.appnav-wrap{
    box-sizing: border-box;
    font-family: sans-serif;
    display: flex;
    flex-direction: row;
    justify-content: space-evenly;

    span{
        color:#fff
    }
    .link a{
        // border-top: 3px solid transparent;
        padding: 4px 8px 4px 8px;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        &:hover{
            background: rgba($accent-color, 0.2);
        }

        span{
            font-size: 9px;
        }
    }
}


@media only screen and (min-width : 600px){
    .company{
        display: block;
        margin: 0;
        padding: 0;
        height: 60px;
        color: #fff;
        font-family: Verdana, Geneva, Tahoma, sans-serif;
        letter-spacing: 0.2em;
        text-align: center;
    }
    .logout{
        width: 100%;
        background-color: rgba(#000, 0.5);
        display: flex;
        justify-content: center;
        align-items: center;
        display: block;
        height: 60px;
        position: absolute;
        bottom: 5px;
        font-family: Verdana, Geneva, Tahoma, sans-serif;

        a{
            height: 100%;
            display: flex;
            justify-content: center;
            align-items: center;
            text-decoration: none;
            color: #fff;
        }
    }
    .active{
        background: rgba($accent-color, 0.2);
        .name{
            color: $accent-color;
        }
    }
    .appnav-wrap{
        display: flex;
        flex-direction: column;

        .link{
            width: 75%;
            margin: auto;
        }

        .link a{
            // border: 0.4px solid #fff;
            width: 100%;
            display: flex;
            flex-direction: row;
            justify-content: flex-start;
            margin: 10px 0px;
            padding: 6px 6px;
            text-decoration: none;
            border-radius: 8px;

            span{
                font-size: 14px;
                margin-left: 14px;
            }
        }
    }
}
</style>