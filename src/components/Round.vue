<template>
    <div class="tournament-bracket__round">
        <h3 class="tournament-bracket__round-title">{{ title || "" }}</h3>
        <!-- UL is the list and li are matches ( between 2 opponents ) -->
        <ul class="tournament-bracket__list">
            <game v-for="game in games" :key="game" :game="game" />
        </ul>
    </div>
</template>


<script>
import Game from "./Game.vue";

export default {
    name: "round",
    components: {
        'game':Game,
    },
    props: ["title", "games"],
};
</script>