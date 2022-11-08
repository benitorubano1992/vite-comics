<script>
export default {
    name: "AppContents",
    data() {
        return {

        }
    }
}
</script>
<template>
    <div class="contents">
        <div class="container">

            <p>--&gt;Contents go Here&lt;--</p>

        </div>

    </div>
</template>
<style lang="scss">
@use "../styles/general.scss" as *;
@use "../styles/partials/variables" as *;
@use"../styles/partials/mixin" as *;

.contents {
    min-height: 150px;
    background-color: $bg-cont;
    color: $bg-header;
    font-weight: bold;

    .container {
        min-height: 150px;
        @include myFlexRow(row, initial, center);
    }
}
</style>