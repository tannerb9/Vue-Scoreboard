<template>
  <h2>{{ message }}</h2>
</template>

<script>
export default {
  name: "ScoreMessage",
  props: {
    teams: Array,
  },
  methods: {
    checkWinner() {
      const [team1, team2] = this.teams;
      let isPlural = true;

      if (team1.score > team2.score) {
        if (team1.score - team2.score === 1) {
          isPlural = false;
        }
        return `${team1.name} is winning by ${team1.score -
          team2.score} point${isPlural ? "s" : ""}!`;
      } else if (team1.score < team2.score) {
        if (team2.score - team1.score === 1) {
          isPlural = false;
        }
        return `${team2.name} is winning by ${team2.score -
          team1.score} point${isPlural ? "s" : ""}!`;
      } else {
        return "The game is tied!";
      }
    },
  },
  computed: {
    message() {
      return this.checkWinner();
    },
  },
};
</script>

<style></style>
