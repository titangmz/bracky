<template>
  <div class="container">
    <h1>Responsive Tournament Bracket</h1>
    <h2>Ice hockey at the 1998 Winter Olympics – Men's tournament</h2>
    <div class="tournament-bracket tournament-bracket--rounded">
      <round
        v-for="(round, index) in value"
        :key="index"
        v-model="round.games"
      >
        <template #game="{ game }">
          <slot name="game" :game="game" /> </template
      ></round>
    </div>
  </div>
</template>


<script>
import Round from "./components/Round.vue";

export default {
  name: "bracket",
  components: {
    round: Round,
  },
  props:['value'],
};
</script>