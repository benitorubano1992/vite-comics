<script>
import { toHandlers } from 'vue';
export default {
    name: "productCard",
    data() {
        return {

        }
    },
    props: {
        imgSrc: String,
        title: String

    }
}
</script>
<template>
    <div class="card">
        <img :src="imgSrc" alt="dc icon">
        <p>{{ title }}</p>
    </div>
</template>
<style lang="scss" scoped>
@use "../styles/general.scss" as *;
@use "../styles/partials/variables" as *;
@use"../styles/partials/mixin" as *;

.card {
    width: calc(100% / 6 - 10px);
    margin-bottom: 1.3rem;
    color: $bg-header;

    p {
        margin-top: 0.8rem;
        text-transform: uppercase;
        font-weight: 100;
        font-size: 0.8rem;
    }
}
</style>