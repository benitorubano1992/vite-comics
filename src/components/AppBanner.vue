<script>
export default {
    name: "AppBanner",
    data() {
        return {

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
    <section class="jumbotron">
        <img :src="getImagePath(`../assets/img/jumbotron.jpg`)" alt="jumbotron image">
    </section>
</template>
<style lang="scss" scoped>
@use "../styles/general.scss" as *;
@use "../styles/partials/variables" as *;
@use"../styles/partials/mixin" as *;

.jumbotron {
    height: 300px;

    img {
        width: 100%;
        height: 100%;
        object-fit: cover;
        object-position: top;
    }

}
</style>