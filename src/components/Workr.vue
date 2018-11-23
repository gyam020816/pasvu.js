<template>
    <div class="workr">
        this is the workr template
        <div class="workr-anchor">
            <div class="wbase"></div>
            <div class="wback"></div>
        </div>
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
        border: 1px solid purple;
    }
    .workr-anchor {
        position: relative;
        width: 200px;
        height: 200px;
        border: 1px solid red;
    }
    .wbase {
        position: absolute;
        bottom: 5px;
        left: 0;
        right: 0;
        margin-left: auto;
        margin-right: auto;

        border-top-left-radius: 20px;
        border-top-right-radius: 40px;
        border-bottom-left-radius: 20px;
        border-bottom-right-radius: 40px;
        border: 4px solid #CC0000;
        background: red;
        width: 100px;
        height: 100px;

        transform: rotate3d(1, 0, 0, 55deg) rotate3d(0, 0, 1, 55deg);
        transition: 1s ease-in-out;
    }
    .workr-anchor:hover > .wbase {
        transform: rotate3d(1, 0, 0, 55deg) rotate3d(0, 0, 1, 235deg);
    }
    .wback {
        position: absolute;
        top: 5px;
        left: 0;
        right: 0;
        margin-left: auto;
        margin-right: auto;

        border-top-left-radius: 40px;
        border-top-right-radius: 20px;
        border-bottom-left-radius: 40px;
        border-bottom-right-radius: 20px;
        border: 4px solid purple;
        background: pink;
        width: 100px;
        height: 100px;

        transform: rotate3d(1, 0, 0, 55deg) rotate3d(0, 0, 1, 55deg) rotate3d(0, 1, 0, 80deg);
        transform-origin: center center 55px;
        transition: 1s ease-in-out;
    }
    .workr-anchor:hover > .wback {
        transform: rotate3d(1, 0, 0, 55deg) rotate3d(0, 0, 1, 235deg) rotate3d(0, 1, 0, 90deg);
    }

</style>
