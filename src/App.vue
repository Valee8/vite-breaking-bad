<script>
import axios from 'axios';
import AppMain from './components/AppMain.vue'
import AppHeader from './components/AppHeader.vue'
import AppFilter from './components/AppFilter.vue'


import { store } from './store.js';

export default {
  name: "App",
  components: {
    AppHeader,
    AppMain,
    AppFilter
  },
  data() {
    return {
      store,
    }
  },
  methods: {
    getCharacters() {

      let myUrl = store.apiURL;

      if (store.select != "") {
        myUrl += `?${store.ApiNameParameter}=${store.select}`;
      }
      else if (store.select === "") {
        this.$emit('filter');
      }

      axios
        .get(myUrl)
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

    <AppFilter @filter="getCharacters" />

    <AppMain />

  </main>

</template>

<style lang="scss">
@use './styles/general.scss' as *;
</style>
