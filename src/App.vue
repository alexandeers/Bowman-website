<script setup>
// import { RouterLink, RouterView } from "vue-router";
// import HelloWorld from "./components/HelloWorld.vue";
import Scoreboard from "./components/Scoreboard.vue";
import Navbar from "./components/Navbar.vue";
</script>

<template>
    <div class="main-layout">
        <Navbar class="navbar"/>
        <Scoreboard class="scoreboard"/>
    </div>
</template>

<style scoped>

.main-layout {
    display: flex;
    flex-direction: row;
    height: 100%;
    width: 100%;
    gap: 1em;
    padding: 0;
    margin: 0;
}

.scoreboard {
    margin: auto;
}

.navbar {
    width: auto;
    background: rgba(0,0,0, 0.3);
    padding: 2em;
    padding-bottom: 0;
    margin: 0;
}

html {
    min-height: 100vh;
    min-width: 100vw;
    overflow-x: hidden;
}

body {
    height: 100% !important;
    width: 100% !important;
}

</style>