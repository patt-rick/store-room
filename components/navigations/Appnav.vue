<template>
    <div class="appnav-main">
        <div class="company">
            <h2>Store-Room</h2>
        </div>
        <div class="appnav-wrap">
            <span class="link">
                <nuxt-link active to="/">
                    <i class="fa-solid fa-chart-simple"></i>
                    <span class="name">Dashboard</span>
                </nuxt-link>
            </span>
            <span class="link">
                <nuxt-link to="/home">
                    <i class="fa-solid fa-house-chimney"></i>
                    <span class="name">Home</span>
                </nuxt-link>
            </span>
            <span class="link">
                <nuxt-link to="/inventory">
                    <i class="fa-solid fa-warehouse"></i>
                    <span class="name">Inventory</span>
                </nuxt-link>
            </span>
            <span class="link">
                <nuxt-link to="/restock">
                    <i class="fa-solid fa-boxes-stacked"></i>
                    <span class="name">Restock</span>
                </nuxt-link>
            </span>
            <span class="link">
                <nuxt-link to="/history">
                    <i class="fa-solid fa-clock-rotate-left"></i>
                    <span class="name">History</span>
                </nuxt-link>
            </span>
        </div>
        <div class="logout link">
            <nuxt-link class="log" to="/login">
                <i class="fa-solid fa-arrow-right-from-bracket"></i>
                <span class="name">Logout</span>
            </nuxt-link>
        </div>
    </div>
</template>
<script>
export default {};
</script>
<style lang="scss">
.appnav-main {
    height: 100%;
    background-color: $primary-color;
    .name,
    .company,
    .logout {
        display: none;
    }
    .appnav-wrap {
        color: #fff;
        height: 100%;
        display: flex;
        justify-content: space-evenly;
        align-items: center;
        font-size: 1.15rem;
    }
}
@media only screen and (min-width: 720px) {
    .appnav-main {
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        align-items: center;
        .logout {
            display: inline-block;
            padding: 20px;
            font-size: 1.2rem;
        }
        .appnav-wrap {
            margin-top: 70px;
            width: 100%;
            height: fit-content;
            padding: 8px;
            display: flex;
            flex-direction: column;
            justify-content: flex-start;
            align-items: center;
            font-size: 1.15rem;

            i {
                padding: 15px 3px;
            }
        }
    }
}
@media only screen and (min-width: 1024px) {
    .appnav-main {
        .name,
        .company,
        .logout {
            display: block;
            font-weight: bold;
        }
        .company {
            padding: 40px 10px 20px 10px;
            color: $accent-color;
        }

        .appnav-wrap {
            margin-top: -150px;
            align-items: flex-start;
            padding: 15px 30px;

            i {
                padding-right: 15px;
            }
        }
    }
    .link a {
        display: flex;
        justify-content: flex-start;
        align-items: center;
    }
}
</style>
