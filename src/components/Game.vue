<template>
  <li class="tournament-bracket__item">
    <div class="tournament-bracket__match" tabindex="0">
      <slot :game="value" name="game" />
    </div>
  </li>
</template>

<script>
export default {
  name: "game",
  props: ["value"],
  watch: {
    value(val) {
      console.log(val);
    },
  },
};
</script>

<style lang="less" scoped src="../assets/game.less" />