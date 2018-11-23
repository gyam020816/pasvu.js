<template>
    <div class="workr">
        this is the workr template
        <div class="workr-anchor">
            <div class="wradius">X</div>
            <div class="wbase">F elt A</div>
            <div class="wback">
                <div class="wback-l">L</div>
                <div class="wback-c">C</div>
                <div class="wback-r">R</div>
            </div>
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
        color: white;
        font-size: 2em;
    }
    .wbase {
        position: absolute;
        bottom: 5px;
        left: 0;
        right: 0;
        margin-left: auto;
        margin-right: auto;
        overflow: hidden;

        border-top-left-radius: 20px;
        border-top-right-radius: 20px;
        border-bottom-left-radius: 40px;
        border-bottom-right-radius: 40px;
        background: black;
        width: 100px;
        height: 100px;

        transform: rotate3d(1, 0, 0, 55deg) rotate3d(0, 0, 1, 55deg) rotate3d(0, 0, 1, -90deg);
        transition: 3s ease-in-out;
    }
    .workr-anchor:hover > .wbase {
        transform: rotate3d(1, 0, 0, 55deg) rotate3d(0, 0, 1, 535deg) rotate3d(0, 0, 1, -90deg);
    }

    .wback {
        position: absolute;
        top: 45px;
        left: 0;
        right: 0;
        margin-left: auto;
        margin-right: auto;

        border: 1px solid red;
        width: 100px;
        height: 75px;

        transform: rotate3d(1, 0, 0, 55deg) rotate3d(0, 0, 1, 55deg) rotate3d(0, 1, 0, 80deg)  rotate3d(0, 0, 1, -90deg);
        transform-origin: center center 55px;
        transition: 3s ease-in-out;
        transform-style: preserve-3d;
    }

    .wback-l, .wback-c, .wback-r {
        position: absolute;
        margin-left: auto;
        margin-right: auto;

        height: 75px;
    }
    .wback-l {
        background: blue;
        width: 30px;
        left: 0;
        right: auto;

        border-top-left-radius: 40px;
        border-bottom-left-radius: 20px;

        transform: rotate3d(0, 1, 0, 10deg);
        transform-origin: right center 0;
    }
    .wback-c {
        background: red;
        width: 40px;
        left: 0;
        right: 0;
    }
    .wback-r {
        border-top-right-radius: 40px;
        border-bottom-right-radius: 20px;
        background: blue;
        width: 30px;
        left: auto;
        right: 0;

        transform: rotate3d(0, 1, 0, -10deg);
        transform-origin: left center 0;
    }
    .workr-anchor:hover > .wback
    {
        transform: rotate3d(1, 0, 0, 55deg) rotate3d(0, 0, 1, 535deg) rotate3d(0, 1, 0, 80deg) rotate3d(0, 0, 1, -90deg);
    }


    .wradius {
        position: absolute;
        top: 145px;
        left: 0;
        right: 0;
        margin-left: auto;
        margin-right: auto;

        border-top-left-radius: 40px;
        border-top-right-radius: 40px;
        border-bottom-left-radius: 20px;
        border-bottom-right-radius: 20px;
        background: blue;
        width: 20px;
        height: 75px;

        transform: rotate3d(1, 0, 0, 55deg) rotate3d(0, 0, 1, 90deg) rotate3d(0, 1, 0, 90deg)  rotate3d(0, 0, 1, -90deg);
        transition: 3s ease-in-out;
    }
</style>
