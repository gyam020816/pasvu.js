<template>
    <div id="app">
        <img alt="Vue logo" src="./assets/logo.png">
        <Workr></Workr>
        <HelloWorld msg="Welcome to Your Vue.js + TypeScript App"/>
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
