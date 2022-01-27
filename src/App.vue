<template>
    <div>
        {{ data.teams }}
        {{ data }}
        <hr />
        <bracket v-model="data">
            <template #game="{ game }">
                <div style="background-color:red">
                  {{ game }}
                </div>
            </template>
        </bracket>
    </div>
</template>

<style>
    body {
        background-color: #f1f1f1;
        font-family: "Work Sans", "Helvetica Neue", Arial, sans-serif;
    }
</style>

<script>
    import Bracket from "./Bracket";
    // import Bracket from '../dist/bracky.common'

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
                teams: ["C1", "C2", "C3", "C4", "C5", "C6", "C7", "C8"],
            };
        },
        methods: {
            magic(e) {
                console.log(e);
                e.player1 = {};
            },
            setTeam(e, a) {
                console.log(e.target.value, a);
                a.name = e.target.value;
            },
        },
    };
</script>
