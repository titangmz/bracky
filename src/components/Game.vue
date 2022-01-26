<template>
  <li class="tournament-bracket__item">
    <div class="tournament-bracket__match" tabindex="0">
      <table class="tournament-bracket__table">
        <!-- <caption class="tournament-bracket__caption">
          <time datetime="1998-02-18">18 February 1998</time>
        </caption> -->
        <thead class="sr-only">
          <tr>
            <th>Team</th>
            <th>Score</th>
          </tr>
        </thead>
        <tbody class="tournament-bracket__content">
          <tr class="tournament-bracket__team tournament-bracket__team--winner">
            <td class="tournament-bracket__country">
              <abbr class="tournament-bracket__code" :title="game.player1.name">{{game.player1.name}}</abbr>
              <!-- <span
                class="tournament-bracket__flag flag-icon flag-icon-ca"
                aria-label="Flag"
              ></span> -->
            </td>
            <td class="tournament-bracket__score">
              <span class="tournament-bracket__number">{{game.player1.score}}</span>
            </td>
          </tr>
          <tr class="tournament-bracket__team">
            <td class="tournament-bracket__country">
              <abbr class="tournament-bracket__code" :title="game.player2.name"
                >{{game.player2.name}}</abbr
              >
              <!-- <span
                class="tournament-bracket__flag flag-icon flag-icon-kz"
                aria-label="Flag"
              ></span> -->
            </td>
            <td class="tournament-bracket__score">
              <span class="tournament-bracket__number">{{game.player2.score}}</span>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </li>
</template>

<script>
export default {
  name: "game",
  props: ["game"],
};
</script>