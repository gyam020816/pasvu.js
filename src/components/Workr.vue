<template>
    <div class="workr">
        this is the workr template
        <div class="wbase"></div>
    </div>
</template>

<script lang="ts">
    import Vue from "vue";

    export default Vue.extend({
        name: "Workr",
        props: {},
    });
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    .workr {
        color: red;
    }
    .wbase {
        border-top-left-radius: 40px;
        border-top-right-radius: 40px;
        border-bottom-left-radius: 20px;
        border-bottom-right-radius: 20px;
        border: 4px solid #CC0000;
        background: red;
        position: relative;
        width: 100px;
        height: 100px;

        transform: rotate3d(1, 0, 0, 55deg) rotate3d(0, 0, 1, 55deg);
        transition: 1s ease-in-out;
    }
    .wbase:hover {
        transform: rotate3d(1, 0, 0, 55deg) rotate3d(0, 0, 1, 235deg);
    }

</style>
