<template>
    <div class="app-header-wrap">
        <span>Company Name</span>
        <div class="main-profile">
            <div class="username">Mitchelle</div>
            <div @click="poplogout" class="profile"></div>
            <div v-show="showlogout" class="logout">
                <nuxt-link to="/login">logout</nuxt-link>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    data() {
        return {
            showlogout: false,
        };
    },
    methods: {
        poplogout() {
            this.showlogout = !this.showlogout;
        },
    },
};
</script>
<style lang="scss">
.app-header-wrap {
    height: 100%;
    display: flex;
    flex-wrap: nowrap;
    justify-content: space-between;
    align-items: center;

    padding: 1px 8px;
    border-bottom: 0.4px solid #efefef;
    font-family: inherit;

    .route {
        text-transform: uppercase;
        color: $accent-color;
    }

    .main-profile {
        position: relative;
        display: flex;
        justify-content: space-evenly;
        align-items: center;
        .username {
            font-weight: 200;
        }
        .logout {
            position: absolute;
            top: 37px;
            left: -36px;
            padding: 6px 15px;
            background: #fff;
            border-radius: 2px;
            border: 0.2px solid #ccc;
            box-shadow: 1px 1px 4px rgba(#000, 0.1);
            cursor: pointer;
        }
    }

    .profile {
        margin-left: 10px;
        height: 40px;
        width: 40px;
        border-radius: 50%;
        overflow: hidden;
        border: 2px solid $accent-color;
        cursor: pointer;
        background-image: url("@/assets/defaultProfile.jpg");
        background-size: cover;
    }
    a {
        text-decoration: none;
        color: #ccc;
    }
}
</style>
