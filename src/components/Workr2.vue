<template>
    <div class="workr" v-on:mousedown="moveOn" v-on:mouseup="moveOff" v-on:mousemove="moveDuring">
        <div class="workr-anchor">
            <span class="label">anchor</span>
            <div class="workr-port" v-bind:style="{ transform: transform }">
                <span class="label">port</span>
                <div class="workr-sample"></div>
                <div class="workr-sample2"></div>

                <Plane x="20" y="40"></Plane>
            </div>
        </div>
    </div>
</template>

<script lang="ts">
    import Vue from "vue";
    import Plane from "@/components/Plane.vue";

    export default Vue.extend({
        name: "Workr",
        props: {},
        components: { Plane },
        data: function() { return {
            transform: "",
            c_rp: 55,
            c_ry: 0,
            c_rr: 0,
            m_x: 0,
            m_y: 0,
            moving: false,
        }},
        methods: {
            updateCam() {
                this.transform = ""
                    + " rotate3d(1, 0, 0, " + this.c_rp + "deg)"
                    + " rotate3d(0, 0, 1, " + this.c_ry + "deg)"
                    + " rotate3d(0, 1, 0, " + this.c_rr + "deg)"
                ;
            },
            moveOn(event) {
                this.m_x = event.clientX;
                this.m_y = event.clientY;
                this.moving = true;
            },
            moveOff(event) {
                this.moving = false;
            },
            moveDuring(event) {
                if (this.moving) {
                    this.c_rp += this.m_y - event.clientY;
                    this.c_ry += this.m_x - event.clientX;
                    this.m_x = event.clientX;
                    this.m_y = event.clientY;
                    this.updateCam()
                }
            }
        },
        created(): void {
            this.updateCam();
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
        user-select: none;
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
        width: 100px;
        height: 100px;

        transform-style: preserve-3d;

        outline: 1px solid red;
    }

    .workr-sample {
        position: absolute;
        width: 20px;
        height: 20px;
        background-color: blue;

        transform:
            translate3d(-10px, -10px, 0)
            translate3d(75px, 75px, 0)
            rotateX(45deg);
        transform-origin: 50% 50% 0;
    }

    .workr-sample2 {
        position: absolute;
        width: 40px;
        height: 40px;
        background-color: red;

        transform:
                translate3d(-20px, -20px, 0)
                translate3d(75px, 75px, 0)
                rotateX(-45deg);
        transform-origin: 50% 50% 0;
    }
</style>
