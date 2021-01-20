<template>
  <form @submit.prevent="submitForm()">
    <input id="rhymeWord" v-model="rhymeWord" placeholder="Word to Rhyme" />
    <button>Submit</button>
  </form>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      rhymeWord: "Apple",
    };
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
