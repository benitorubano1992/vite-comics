<script>
export default {
    name: "AppHeader",
    data() {
        return {
            imageName: "dc-logo.png",
            linksPage: ["Characters", "Comics", "Movies", "TV", "Games", "Collectibles", "Videos", "Fans", "News", "Shop"],
            currentElement: 1
        }
    },
    methods: {
        getImagePath(imagePath) {
            return new URL(imagePath, import.meta.url).href;
        }
    }

}</script>
<template>
    <header>
        <div class="container">
            <div class="row">
                <div class="logo"><img :src="getImagePath(`../assets/img/${imageName}`)" alt=""></div>

                <nav>
                    <ul>
                        <li v-for="(link, index) in this.linksPage" :class="{ active: currentElement === index }">
                            <a href="#">{{ link }}</a>
                        </li>
                    </ul>
                </nav>
            </div>
        </div>

    </header>
</template>
<style lang="scss" scoped>
@use "../styles/general.scss" as *;
@use "../styles/partials/variables" as *;
@use"../styles/partials/mixin" as *;

header {
    background-color: $bg-header;
    height: 120px;

    .row {
        @include myFlexRow(row, space-between, center);

        ul {
            @include myFlexRow(row, initial, center);

            li {
                font-size: 0.6rem;
                font-weight: bold;
                text-transform: uppercase;
                line-height: 120px;
                position: relative;

                &.active {
                    color: $bg-product;
                }

                &.active::after {
                    content: "";
                    display: block;
                    width: 100%;
                    height: 3px;
                    background-color: $bg-product;
                    position: absolute;
                    bottom: 0;
                    left: 0;
                }

                &:not(:last-child) {
                    margin-right: 1.5rem;
                }

            }

        }


    }

}
</style>