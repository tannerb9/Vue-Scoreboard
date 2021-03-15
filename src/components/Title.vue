<template>
  <h1>
    <span class="{winning: teams[0].winning}">{{ teams[0].name }}</span>
    vs
    <span class="{winning: teams[1].winning}">{{ teams[1].name }}</span>
  </h1>
</template>

<script>
export default {
  props: { teams: Array },
};
</script>

<style></style>
