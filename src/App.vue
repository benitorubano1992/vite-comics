<script>
import AppHeader from './components/AppHeader.vue';
import AppProducts from './components/AppProducts.vue';
import AppFooter from './components/AppFooter.vue';
import AppContents from './components/AppContents.vue';

export default {
  data() {
    return {

    }
  },
  components: {
    AppHeader,
    AppProducts,
    AppFooter,
    AppContents
  }
}</script>
<template>
  <AppHeader />
  <AppContents />
  <AppProducts />
  <AppFooter />

</template>
<style lang="scss">
@use "./styles/general.scss" as *;
@use "./styles/partials/variables.scss" as *;
</style>