<script>

import productCard from './productCard.vue';
export default {
    name: "ProductList",
    components: {
        productCard,
    },
    data() {
        return {
            listApi: [],


        }
    },
    created: function () {
        fetch("../dc-comics.json")
            .then(response => response.json())
            .then(data => this.listApi = data)
    }



}





</script>
<template>
    <section class="product-box">
        <div class="container">
            <productCard v-for="(item, index) in listApi" key="index" :imgSrc="item.thumb" :title="item.series" />
        </div>
        <a href="#" class="btn btn-abs">Current Series</a>
        <a href="#" class="btn btn-center">Load more</a>
    </section>

</template>
<style lang="scss" scoped>
@use "../styles/general.scss" as *;
@use "../styles/partials/variables" as *;
@use"../styles/partials/mixin" as *;

.product-box {
    background-color: black;
    padding: 3rem 0;
    position: relative;
    display: flex;
    flex-direction: column;
    justify-content: center;

    .container {

        @include myFlexRow(row, space-between, initial);
        flex-wrap: wrap;
    }

    .btn {
        padding: 0.5rem 0.8rem;
        background-color: $bg-product;
        color: $bg-header;
        text-transform: uppercase;
        font-weight: bold;

        &-abs {
            position: absolute;
            top: -15px;
            left: 5%;
        }

        &-center {
            align-self: center;
            padding: 0.3rem 2rem;
        }


    }



}
</style>