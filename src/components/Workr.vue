<template>
    <div class="workr">
        this is the workr template {{transform}}
        <div class="workr-anchor">
            <span class="label">anchor</span>
            <div class="workr-port" v-bind:style="{ transform: transform }">
                <span class="label">port</span>
                <div class="workr-mobile">
                    <span class="label">mobile</span>
                    <div class="wbase">F elt A</div>
                    <div class="wback">
                        <span class="label">back</span>
                        <div class="wback-l">L</div>
                        <div class="wback-c">C</div>
                        <div class="wback-r">R</div>
                    </div>
                </div>
                <div class="workr-static">
                    <span class="label">static</span>
                    <div class="wradius"></div>
                    <div class="wfeet"></div>
                </div>
            </div>
        </div>
        <input v-model="c_rp" type="number" min="-360" max="360" v-on:change="cam" v-on:click="cam">
        <input v-model="c_ry" type="number" min="-360" max="360" v-on:change="cam" v-on:click="cam">
        <input v-model="c_rr" type="number" min="-360" max="360" v-on:change="cam" v-on:click="cam">
    </div>
</template>

<script lang="ts">
    import Vue from "vue";

    export default Vue.extend({
        name: "Workr",
        props: {},
        data: function() { return {
            transform: "",
            c_rp: 55,
            c_ry: 0,
            c_rr: 0,
        }},
        methods: {
            cam(): void {
                this.transform = ""
                    + " rotate3d(1, 0, 0, " + this.c_rp + "deg)"
                    + " rotate3d(0, 0, 1, " + this.c_ry + "deg)"
                    + " rotate3d(0, 1, 0, " + this.c_rr + "deg)"
                ;
            }
        },
        created(): void {
            this.cam();
        }
    });
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    .label {
        position: absolute;
        top: 0;
        right: 0;
        color: red;
        font-size: 20px;
    }

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

    .workr-port {
        position: relative;
        width: 200px;
        height: 200px;

        transform-style: preserve-3d;

        outline: 1px solid red;
    }

    .workr-mobile {
        position: absolute;
        width: 200px;
        height: 200px;

        transform-style: preserve-3d;
        transition: 3s ease-in-out;
        transform: rotate3d(0, 0, 1, 55deg);

        outline: 1px solid blue;
    }

    .workr-static {
        position: absolute;
        width: 200px;
        height: 200px;

        transform-style: preserve-3d;
        outline: 1px solid blue;
    }

    .workr-anchor:hover * .workr-mobile {
        transform: rotate3d(0, 0, 1, 535deg);
    }

    .wbase {
        position: absolute;
        left: 50px;
        top: 50px;

        border-top-left-radius: 20px;
        border-top-right-radius: 20px;
        border-bottom-left-radius: 40px;
        border-bottom-right-radius: 40px;
        background: black;
        width: 100px;
        height: 100px;
    }

    .wback {
        position: absolute;
        top: 45px;
        left: 0;
        right: 0;
        margin-left: auto;
        margin-right: auto;

        width: 100px;
        height: 75px;

        transform: rotate3d(0, 0, 1, 90deg) rotate3d(0, 1, 0, 80deg) rotate3d(0, 0, 1, -90deg);
        transform-origin: center center 55px;
        transform-style: preserve-3d;
        transition: 3s ease-in-out;

        outline: 1px solid green;
    }

    .wback-l, .wback-c, .wback-r {
        position: absolute;
        margin-left: auto;
        margin-right: auto;

        height: 75px;
        background: black;
    }

    .wback-l {
        width: 30px;
        left: 0;
        right: auto;

        border-top-left-radius: 40px;
        border-bottom-left-radius: 20px;

        transform: rotate3d(0, 1, 0, 10deg);
        transform-origin: right center 0;
    }

    .wback-c {
        width: 40px;
        left: 0;
        right: 0;
    }

    .wback-r {
        border-top-right-radius: 40px;
        border-bottom-right-radius: 20px;
        width: 30px;
        left: auto;
        right: 0;

        transform: rotate3d(0, 1, 0, -10deg);
        transform-origin: left center 0;
    }


    .wradius {
        position: absolute;
        right: 90px;
        bottom: -10px;

        border-top-left-radius: 40px;
        border-top-right-radius: 40px;
        border-bottom-left-radius: 20px;
        border-bottom-right-radius: 20px;
        background: blue;
        width: 20px;
        height: 75px;

        transform: rotate3d(0, 0, 1, 90deg) rotate3d(0, 1, 0, 90deg) rotate3d(0, 0, 1, -90deg);
    }
</style>
