<template>
  <div
    class="tournament-bracket__round tournament-bracket__round--quarterfinals"
  >
    <h3 class="tournament-bracket__round-title">Quarterfinals</h3>
    <ul class="tournament-bracket__list">
      <game v-for="(game,index) in games" :key="index" :game="game" />
    </ul>
  </div>
</template>


<script>
import Game from "./Game.vue";

export default {
  name: "round",
  components: {
    game: Game,
  },
  props: ["games"],
};
</script>