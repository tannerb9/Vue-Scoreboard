<template>
  <div>
    <div>
      <h1 class="score">{{ team.score }}</h1>
      <button @click="subtractPoint" :disabled="team.score === 0">
        -
      </button>
      <button @click="addPoint">
        +
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: "ScoreCard",
  props: { team: Object },
  methods: {
    addPoint() {
      this.$emit("add-point", this.team);
    },
    subtractPoint() {
      this.$emit("subtract-point", this.team);
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
