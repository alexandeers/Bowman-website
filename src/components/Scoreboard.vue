<script setup>
// import { RouterLink, RouterView } from "vue-router";
// import HelloWorld from "./components/HelloWorld.vue";
import Slot from "./Slot.vue";
import scoreboard from "../assets/scoreboard.json"

//Create an array of players from the scoreboard.json file
const players = scoreboard.players;
//Convert players to an array
const playersArray = Object.keys(players).map((key) => players[key]);
//Sort the players by points
const sortedPlayers = playersArray.sort((a, b) => b.points - a.points);
</script>

<template>
  <div>
    <h1>Leaderboard</h1>
    <div class="leaderboard">
      <ul>
        <li v-for="player in sortedPlayers" :key="player.name">
          <span>{{ sortedPlayers.indexOf(player) + 1 }}</span>
          <Slot class="slot"
            :name="player.name"
            :points="player.points"
            :kills="player.kills"
            :secondsAlive="player.secondsAlive"
            :damageInflicted="player.damageInflicted"
            :levelsAttained="player.levelsAttained"/>
        </li>
      </ul>
    </div>
  </div>
</template>

<style scoped>

h1 {
  font-size: 3rem;
  margin: auto;
  text-align: center;
  font-weight: bolder;
}

.leaderboard {
  display: flex;
  flex-direction: column;
  height: auto;
  width: min(100vh, 40em);
  padding: auto;
  align-self: center;
  margin: auto;
  padding: auto;
}

li {
  display: flex;
  flex-direction: row;
  gap: 1em;
  text-align: center;
  vertical-align: center;
  height: auto;
  margin: 0;
}

li > span {
  margin: auto;
  font-size: 1.5rem;
}

ul {
  display: flex;
  flex-direction: column;
  height: auto;
  width: 40em;
  padding: auto;
  align-self: center;
  margin: auto;
  padding: auto;
}

.slot {
  margin-block: 0.5em;
  flex-basis: 1;
  flex-grow: 1;
  flex-shrink: 0;
  text-align: left;
  vertical-align: baseline;
}

</style>