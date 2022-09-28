<template>
    <div>
        <div class="table-wrap">
            <div class="table-head">
                <div class="items">Items</div>
                <div class="quantity">Quantity</div>
            </div>
            <div class="not-scroll">
                <div v-for="msg in txt" :key="msg.value" class="table-body">
                    <div class="item-name">{{ msg.message }}</div>
                    <div class="item-quantity">{{ msg.value }}</div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            txt: [
                { message: "crime", value: 43 },
                { message: "three", value: 43 },
                { message: "four", value: 43 },
                { message: "five", value: 43 },
                { message: "six", value: 43 },
                { message: "one", value: 43 },
                { message: "crime", value: 43 },
                { message: "three", value: 43 },
                { message: "four", value: 43 },
                { message: "five", value: 43 },
                { message: "six", value: 43 },
            ],
        };
    },
};
</script>

<style lang="scss">
.not-scroll {
    max-height: 300px;
    overflow: scroll;
    -ms-overflow-style: none;
    scrollbar-width: none;
}
.not-scroll::-webkit-scrollbar {
    display: none;
}
.table-wrap {
    background-color: #fff;
    width: 250px;
    padding: 10px;
    border-radius: 8px;
    box-shadow: 0.5px 0.5px 4px rgba(#000, 0.2);

    display: flex;
    flex-direction: column;
    justify-content: flex-start;

    .table-head {
        width: 100%;
        border-bottom: 3px solid #ccc;
        display: flex;
        justify-content: flex-start;
        align-items: center;
        height: 35px;

        .items {
            border-right: 1px solid #ccc;
            width: 70%;
            height: 35px;
            display: flex;
            justify-content: center;
            align-items: center;
        }
        .quantity {
            width: 30%;
            display: flex;
            justify-content: center;
            align-items: center;
        }
    }

    .table-body {
        width: 100%;
        border-bottom: 1px solid #ccc;
        display: flex;
        justify-content: flex-start;
        align-items: center;
        height: 40px;

        .item-name {
            border-right: 1px solid #ccc;
            width: 70%;
            height: 40px;
            display: flex;
            justify-content: center;
            align-items: center;
        }
        .item-quantity {
            width: 30%;
            display: flex;
            justify-content: center;
            align-items: center;
        }
    }
}
</style>
