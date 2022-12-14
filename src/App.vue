<script>
import axios from 'axios';
import AppMain from './components/AppMain.vue'
import AppHeader from './components/AppHeader.vue'


import { store } from './store.js';

export default {
  name: "App",
  components: {
    AppHeader,
    AppMain
  },
  data() {
    return {
      store,
    }
  },
  methods: {
    getCharacters() {
      axios
        .get(store.apiURL)
        .then(res => {
          store.characterList = res.data.results;
        })
        .catch(error => {
          console.log("Errori: ", error);
        });
    }
  },
  mounted() {
    this.getCharacters();
  }
}
</script>

<template>

  <AppHeader />

  <main>

    <AppMain />

  </main>

</template>

<style lang="scss">
@use './styles/general.scss' as *;
</style>
