<template>
    <div class="tournament-bracket tournament-bracket--rounded">
        <round v-for="(round, index) in value" :key="index" :title="round.title" v-model="round.games">
            <template #game="{ game }"> <slot name="game" :game="game" /> </template
        ></round>
    </div>
</template>

<script>
    import Round from "./components/Round.vue";

    export default {
        name: "bracket",
        components: {
            round: Round,
        },
        props: ["value"],
    };
</script>

<style lang="less" scoped src="./assets/bracket.less" />
