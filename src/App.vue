<template>
    <div>
        <bracket :data="rounds" />
    </div>
</template>

<script>
import Bracket from "./Bracket";

const rounds = [
    //Semi finals
    {
        title: "Semifinals",
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
        title: "Final",
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
        // Bracket,
        bracket: Bracket,
    },
    data() {
        return {
            rounds: rounds,
        };
    },
};
</script>
