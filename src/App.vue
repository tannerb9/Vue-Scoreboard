<template>
  <div id="app">
    <Title :teams="teams" />
    <ScoreMessage :teams="teams" />
    <div>
      <template v-for="team in teams">
        <ScoreCard
          :key="team.name"
          :team="team"
          @add-point="handleAddPoint"
          @subtract-point="handleSubtractPoint"
        />
      </template>
    </div>
    <ScoreCard />
  </div>
</template>

<script>
import Title from "./components/Title.vue";
import ScoreMessage from "./components/ScoreMessage";
import ScoreCard from "./components/ScoreCard.vue";

export default {
  name: "App",
  components: {
    Title,
    ScoreMessage,
    ScoreCard,
  },
  data() {
    return {
      teams: [
        { name: "Team 1", score: 0, winning: false },
        { name: "Team 2", score: 0, winning: false },
      ],
      leaderboardMessage: "",
    };
  },
  methods: {
    checkWinner() {
      const [team1, team2] = this.teams;
      if (team1.score > team2.score) {
        team1.winning = true;
        team2.winning = false;
      } else if (team2.score > team1.score) {
        team2.winning = true;
        team1.winning = false;
      } else {
        team1.winning = false;
        team2.winning = false;
      }
    },
    handleAddPoint(team) {
      team.score++;
      this.checkWinner();
    },
    handleSubtractPoint(team) {
      team.score !== 0 && team.score--;
      this.checkWinner;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
