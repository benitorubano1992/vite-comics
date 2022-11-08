<script>
export default {
    name: "AppFooter",
    data() {
        return {
            comicsList: ["Characters", "Comics", "Movies", "TV", "Games", "Collectibles", "Videos", "Fans", "News"],
            shop: ["Shop Dc", "Shop DC Collectibles"],
            Dc: ["Terms of Use", "Privacy policy(New)", "Ad Choices", "Advertising", "Jobs", "Subscriptions", "Talent Workshow", "Cps Certificates", "Shop Help", "Contact Us"],
            Sites: ["DC", "Mad Magazine", "DC kids", "DC Universe", "DC Power Visa"],
            imgList: ["footer-facebook.png", "footer-periscope.png", "footer-pinterest.png", "footer-twitter.png", "footer-youtube.png"]
        }
    },
    methods: {
        getImagePath(imagePath) {
            return new URL(imagePath, import.meta.url).href;
        }
    }

}</script>
<template>
    <footer>
        <div class="footer-top">
            <div class="container">
                <div class="row">
                    <div class="list-item">
                        <div class="col">
                            <div>
                                <h3>DC COMIC</h3>
                                <ul>
                                    <li v-for="(comic, index) in comicsList">
                                        <small><a href="http:#">{{ comic }}</a></small>
                                    </li>
                                </ul>
                            </div>

                            <div class="shop-list">
                                <h3>SHOP</h3>
                                <ul>
                                    <li v-for="item in shop"><small><a href="#">{{ item }}</a></small></li>
                                </ul>
                            </div>

                        </div>

                        <div class="col">
                            <div>
                                <h3>DC</h3>
                                <ul>
                                    <li v-for="item in Dc">
                                        <small><a href="http:#">{{ item }}</a></small>
                                    </li>
                                </ul>
                            </div>

                        </div>
                        <div class="col">
                            <div>
                                <h3>Sites</h3>
                                <ul>
                                    <li v-for="item in Sites">
                                        <small><a href="http:#">{{ item }}</a></small>
                                    </li>
                                </ul>
                            </div>

                        </div>



                    </div>
                    <div class="big-icon">
                        <img src="../assets/img/dc-logo-bg.png" alt="logo Dc Big">
                    </div>








                </div>
            </div>
        </div>
        <div class="footer-bottom">
            <div class="container">
                <div class="row">
                    <a href="#" class="btn">SIGN UP NOW</a>
                    <ul class="contact-list">
                        <p>Follow Us</p>
                        <li v-for="img in imgList">
                            <a href="#"><img :src="getImagePath(`../assets/img/${img}`)" alt="social Media Icon"></a>
                        </li>


                    </ul>
                </div>
            </div>
        </div>
    </footer>
</template>
<style lang="scss" scoped>
@use "../styles/general.scss" as *;
@use "../styles/partials/variables" as *;
@use"../styles/partials/mixin" as *;

footer {
    background-image: url(../assets/img/footer-bg.jpg);
    background-size: cover;
    position: relative;

    .footer-top {
        color: $bg-header;
        min-height: 450px;
        overflow-y: hidden;


        .row {
            @include myFlexRow(row, space-between, flex-start);
            padding-top: 1rem;

            .list-item {
                @include myFlexRow(row, init, );

                .col:not(:first-child) {
                    margin-left: 1.2rem;
                }

                .shop-list {
                    margin-top: 1rem;
                }

                h3 {
                    margin-bottom: 1rem;
                }

                ul {
                    font-size: 0.8rem;
                    font-weight: 500;
                    color: grey;

                    li {
                        margin-bottom: 0.5rem;
                    }
                }
            }


            img {
                position: relative;
                top: -100px;
            }


        }
    }

    .footer-bottom {
        color: white;
        background-color: $bg-footer-bottom;
        padding: 1.5rem 0;
        position: absolute;
        bottom: 70px;
        left: 0;
        width: 100%;

        .row {
            @include myFlexRow(row, space-between, center);

            .btn {
                border: 1px solid $bg-product;
                padding: 0.5rem 1rem;
            }

            ul {
                @include myFlexRow(row, initial, center);

                &>* {
                    margin-left: 1.5rem;
                }

                p {
                    color: $bg-product;
                    text-transform: uppercase;
                    font-weight: 600;
                }

            }
        }
    }


}
</style>