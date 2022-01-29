
# Bracky

Single elimination brackets component for vuejs 



## Demo

![Demo](https://raw.githubusercontent.com/titangmz/bracky/main/docs/1.png)

You can style the boxes however you want

## Usage/Examples

```bash
yarn add bracky
```
or

```bash
npm install bracky

```

```javascript
<Bracket v-model="rounds">
    <template #game="{ game }">
    {{game}}
    </template>
</Bracket>
```

```javascript
<script>
import Bracket from "bracky";


const rounds = [
  //Semi finals
  {
    games: [
      {
        player1: { id: "1", name: "Competitor 1", winner: false, score: 2 },
        player2: { id: "4", name: "Competitor 4", winner: true, score: 2 },
      },
      {
        player1: { id: "5", name: "Competitor 5", winner: false, score: 2 },
        player2: { id: "8", name: "Competitor 8", winner: true, score: 2 },
      },
    ],
  },
  //Third place play off
  {
    games: [
      {
        player1: { id: "1", name: "Competitor 1", winner: false, score: 2 },
        player2: { id: "5", name: "Competitor 5", winner: true, score: 2 },
      },
    ],
  },
  //Final
  {
    games: [
      {
        player1: { id: "4", name: "Competitor 4", winner: false, score: 2 },
        player2: { id: "8", name: "Competitor 8", winner: true, score: 2 },
      },
    ],
  },
];

export default {
  components: {
    Bracket,
  },
  data() {
    return {
      rounds: rounds,
    };
  },
};
</script>
```




## Credits
Based on “Responsive Tournament Bracket” by Jakub Hájek:

https://codepen.io/jimmyhayek/embed/yJkdEB?height=563&theme-id=178&slug-hash=yJkdEB&default-tab=result&user=jimmyhayek&embed-version=2&pen-title=Responsive%20Tournament%20Bracket&name=cp_embed_5#css-box