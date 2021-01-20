<template>
  <table border="1px" align="center" id="app">
    <tr>
      <td>Word</td>
      <td>Score</td>
    </tr>
    <tr v-for="item in wordList" v-bind:key="item">
      <td>{{ item.word }}</td>
      <td>{{ item.score }}</td>
    </tr>
  </table>
</template>

<script>
export default {
  name: "WordList",
  props: {
    wordList: Array,
  },
};
</script>
<style>
#app {
  margin-top: 60px;
}
</style>
