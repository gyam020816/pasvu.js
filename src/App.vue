<template>
    <div id="app">
        <Workr></Workr>
    </div>
</template>

<script lang="ts">
    import Vue from "vue";
    import HelloWorld from "./components/HelloWorld.vue";
    import Workr from "@/components/Workr.vue";

    export default Vue.extend({
        name: "app",
        components: {
            HelloWorld, Workr
        }
    });
</script>

<style>
    #app {
        font-family: 'Avenir', Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;
        margin-top: 60px;
    }
</style>
