<template>
  <div
    class="tournament-bracket__round tournament-bracket__round--quarterfinals"
  >
    <!-- <h3 class="tournament-bracket__round-title">Quarterfinals</h3> -->
    <ul class="tournament-bracket__list">
      <game v-for="(game, index) in value" :key="index" :value="game">
        <template #game="{ game }">
          <slot name="game" :game="game" />
        </template>
      </game>
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
  props: ["value"],
};
</script>