<template>
    <div class="tournament-bracket__round">
        <h3 class="tournament-bracket__round-title">&zwnj;{{ title }}</h3>
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
        props: ["value", "title"],
    };
</script>

<style lang="less" scoped src="../assets/round.less" />
