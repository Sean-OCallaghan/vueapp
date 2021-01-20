<template>
  <div id="app">
    <h3>Type a Word to see its Rhymes</h3>
    <form @submit.prevent="getRhymes">
      <input type="text" name="word" placeHolder="word" />
      <button>submit</button>
    </form>
    <h3>Type a Word to see What it sounds Like</h3>
    <form @submit.prevent="getAdjectives">
      <input type="text" name="word" placeHolder="word" />
      <button>submit</button>
    </form>
    <WordList :wordList="list" />
  </div>
</template>

<script>
import Vue from "vue";
import axios from "axios";
import VueAxios from "vue-axios";
Vue.use(VueAxios, axios);
import WordList from "./components/wordList";
export default {
  name: "App",
  components: {
    WordList,
  },
  data() {
    return {
      name: "",
      list: undefined,
    };
  },
  methods: {
    getRhymes(submitEvent) {
      this.name = submitEvent.target.elements.word.value;
      Vue.axios
        .get(`https://api.datamuse.com/words?rel_rhy=` + this.name)
        .then((resp) => {
          this.list = resp.data;
          console.warn(resp.data);
        });
    },
    getAdjectives(submitEvent) {
      this.name = submitEvent.target.elements.word.value;
      Vue.axios
        .get(`https://api.datamuse.com/words?sl=` + this.name)
        .then((resp) => {
          this.list = resp.data;
          console.warn(resp.data);
        });
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
