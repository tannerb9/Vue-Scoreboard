<template>
  <div>
    <div class="hello">
      <h1><span>Team 1</span> vs <span>Team 2</span></h1>
      <h3></h3>
    </div>
    <div>
      <div>
        <title></title>
        <button>-</button>
        <button>+</button>
      </div>
      <div>
        <title></title>
        <button>-</button>
        <button>+</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  data() {
    return {};
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
