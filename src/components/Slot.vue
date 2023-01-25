<script setup>
import { ref, reactive, defineProps } from 'vue';
import { Collapse } from 'vue-collapsed';

const props = defineProps({
    name: String,
    points: Number,
    kills: Number,
    secondsAlive: Number,
    damageInflicted: Number,
    levelsAttained: Number
})

const configuration = reactive({
    displayStats: false
});

function ToggleDisplay() {
    configuration.displayStats = !configuration.displayStats;
    console.log(configuration.displayStats);
}

</script>

<template>
    <div class="main">
        <div class="main-stats">
            <p class="main-stat-display name" :class="{ displayStats: configuration.displayStats }" @click="ToggleDisplay">{{ props.name }}</p>
            <p class="main-stat-display" :class="{ greenText: configuration.displayStats }" >{{  props.points  }}</p>
        </div>

        <div>
            <Collapse :when="configuration.displayStats" class="v-collapse">
                <div class="stats" :class="{ scaleStats: configuration.displayStats, opacity100: configuration.displayStats }">
                    <div class="stat-display"><span class="text-white">{{ props.kills }}</span> Kills</div>
                    <div class="stat-display"><span class="text-white">{{ props.secondsAlive }}</span> Seconds Alive</div>
                    <div class="stat-display"><span class="text-white">{{ props.damageInflicted }}</span> Damage Inflicted</div>
                    <div class="stat-display"><span class="text-white">{{ props.levelsAttained }}</span> Levels Attained</div>
                </div>
            </Collapse>
        </div>
    </div>
</template>

<style scoped>
.v-collapse {
    transition: height 300ms cubic-bezier(0.33, 1, 0.68, 1);
}
.main {
    outline: 1px solid white;
    border-radius: 1px;
    padding: 0.5em;
    overflow: hidden;
}

.opacity100 {
    opacity: 100% !important;
}

.displayStats::after {
    height: 100% !important;
    width: 100% !important;
}

.displayStats {
    color: #41b883 !important;
    font-weight: bold !important;
    z-index: 1;
}

.greenText {
    color: #41b883 !important;
}

.name {
    font-weight: lighter;
    color: var(--color-text);
    background: transparent;
    cursor: pointer;

    transition: 
        font-weight 50ms ease-out,
        color 200ms ease-out,
        background 200ms ease-out;
}

.name::after {
    content: "";
    position: absolute;
    bottom: 0;
    left: 0;

    transition: 200ms cubic-bezier(0.33, 1, 0.68, 1);
    width: 100%;
    height: 0px;
    background: white;
    z-index: -1;
}

.name:hover::after {
    width: 100%;
}

.name:hover {
    font-weight: 600;
    background: hsl(0, 0%, 20%);
    color: white;
}

.stats {
    grid-template-columns: 1fr 1fr;
    overflow: hidden;
    display: grid;
    gap: 0em;
    opacity: 0%;

    transition: opacity 300ms cubic-bezier(0.33, 1, 0.68, 1);
}

.stat-display {
    border-bottom: 1px solid white;
    margin-inline: 0.25em;
    margin: 1em;
    overflow: hidden;
}

.main-stats {
    flex-direction: row;
    font-weight: bold;
    font-size: 2em;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 0.5em;
}

.main-stat-display {
    margin: 0;
    /* mix-blend-mode: difference; */
    padding-inline: 0.25em;
    user-select: none;
}
</style>