<template>
  <div>
    {{ data.teams }}
    {{ data }}
    <bracket v-model="data">
      <template #game="{ game }">
        <div>
          <select v-on:input="setTeam($event, game.player1)" name="cars" id="cars">
            <option v-for="team in teams" :key="team" :value="team">{{team}}</option>
          </select>
          <br />
          {{ game.player2.name }} - {{ game.player2.score }}
        </div>
      </template>
    </bracket>
  </div>
</template>

<script>
import Bracket from "./Bracket";


const data = [
  //quads
  {
    
    games: [
      {
        player1: { id: "1", name: "CP1", winner: true, score: 3 },
        player2: { id: "4", name: "CP4", winner: false, score: 0 },
      },
      {
        player1: { id: "5", name: "CP5", winner: false, score: 1 },
        player2: { id: "8", name: "CP8", winner: true, score: 2 },
      },
      {
        player1: { id: "5", name: "CP5", winner: false, score: 1 },
        player2: { id: "8", name: "CP8", winner: true, score: 2 },
      },
      {
        player1: { id: "5", name: "CP5", winner: false, score: 1 },
        player2: { id: "8", name: "CP8", winner: true, score: 2 },
      },
    ],
  },
  //Semi finals
  {
    games: [
      {
        player1: { id: "1", name: "CP1", winner: true, score: 3 },
        player2: { id: "4", name: "CP4", winner: false, score: 0 },
      },
      {
        player1: { id: "5", name: "CP5", winner: false, score: 1 },
        player2: { id: "8", name: "CP8", winner: true, score: 2 },
      },
    ],
  },
  //Final
  {
    games: [
      {
        player1: { id: "4", name: "CP4", winner: false, score: 2 },
        player2: { id: "8", name: "CP8", winner: true, score: 1 },
      },
    ],
  },
  {
    games: [
      {
        player1: { id: "4", name: "CP4", winner: false, score: 2 },
        player2: { id: "8", name: "CP8", winner: true, score: 1 },
      },
    ],
  },
];

export default {
  name: "app",
  components: {
    bracket: Bracket,
  },
  data() {
    return {
      data: data,
      teams:["C1", "C2", "C3", "C4", "C5", "C6", "C7", "C8"],
    };
  },
  methods: {
    magic(e) {
      console.log(e);
      e.player1 = {};
    },
    setTeam(e,a){
        console.log(e.target.value,a)
        a.name = e.target.value
    }
  },
};
</script>
