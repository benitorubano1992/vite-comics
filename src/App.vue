<script>
import AppHeader from './components/AppHeader.vue';
import AppProducts from './components/AppProducts.vue';
import AppFooter from './components/AppFooter.vue';
import AppContents from './components/AppContents.vue';
import AppBanner from './components/AppBanner.vue';
import ProductList from './components/ProductList.vue';
export default {
  data() {
    return {

    }
  },
  components: {
    AppHeader,
    AppProducts,
    AppFooter,
    AppContents,
    AppBanner,
    ProductList
  }
}
</script>
<template>
  <AppHeader />
  <AppBanner />
  <ProductList />

  <AppProducts />
  <AppFooter />

</template>
<style lang="scss">
@use "./styles/general.scss" as *;
@use "./styles/partials/variables.scss" as *;
</style>