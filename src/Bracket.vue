<template>
    <div class="bcontainer">
        <div class="tournament-bracket tournament-bracket--rounded">
            <round v-for="round in data" :key="round" :games="round.games" :title="round.title" />
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
    props: ["data"],
};
</script>