<template>
  <div id="app">
    <Characters v-bind:characters="characters"/>
  </div>
</template>

<script>
import Characters from "./components/Characters.vue";
import axios from 'axios';
export default {
  name: "App",
  data() {
    return {
      characters: []
    }
  },
  components: {
    Characters
  },
  beforeCreate() {
    axios
    .get('http://hp-api.herokuapp.com/api/characters')
    .then(response => {
      this.characters = response.data;
    })
    .catch(error => {
      console.log(error)
    })
  }
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
