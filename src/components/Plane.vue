<template>
    <div class="workr-plane" v-bind:style="{
        transform: transform,
        width: xs + 'px',
        height: ys + 'px'
    }"></div>
</template>

<script lang="ts">
    import Vue from "vue";

    export default Vue.extend({
        name: "Plane",
        props: {
            x: String,
            y: String
        },
        data: function() { return {
            transform: "",
            xs: 0,
            ys: 0
        }},
        created(): void {
            this.xs = parseInt(this.x);
            this.ys = parseInt(this.y);
            this.transform = ""
                + " translate(" + (-this.xs/2) + "px, " + (-this.ys/2) + ", 0)"
            ;
        }
    });
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    .workr-plane {
        position: absolute;
        background-color: purple;
    }
</style>
