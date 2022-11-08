<script>
export default {
    name: "AppProducts",
    data() {
        return {
            products: [{
                name: "Digital Comics",
                imgName: "buy-comics-digital-comics.png"
            },
            {
                name: "Dc Merchandise",
                imgName: "buy-comics-merchandise.png"
            },
            {
                name: "Subscription",
                imgName: "buy-comics-subscriptions.png"
            },
            {
                name: "Comic Shop Locator",
                imgName: "buy-comics-shop-locator.png"
            },
            {
                name: "Dc Pomer Visa",
                imgName: "buy-dc-power-visa.svg"
            }
            ]
        }
    },
    methods: {
        getImagePath(imagePath) {
            return new URL(imagePath, import.meta.url).href;
        }
    }
}
</script>
<template>
    <section class="product-list">
        <div class="container">
            <div class="row">
                <ul>
                    <li v-for="(product, index) in products">
                        <img :src="getImagePath(`../assets/img/${product.imgName}`)" alt="product image">
                        <p>{{ product.name }}</p>
                    </li>
                </ul>
            </div>
        </div>
    </section>
</template>
<style lang="scss" scoped>
@use "../styles/general.scss" as *;
@use "../styles/partials/variables" as *;
@use"../styles/partials/mixin" as *;

.product-list {
    background-color: $bg-product ;
    color: white;

    ul {
        @include myFlexRow(row, center, center);
        padding: 2rem 1rem;

        li {
            width: 20%;
            display: flex;
            align-items: center;
            font-size: 0.6rem;
            text-transform: uppercase;
            margin-right: 2rem;

            &:first-child {
                margin-left: 0.8rem;
            }

            &:last-child {
                margin-left: 0.5rem;
            }

            img {
                height: 50px;
                margin-right: 0.8rem;
            }
        }

    }


}
</style>