<script>
import { store } from "./store";
import axios from 'axios';
import AppHeader from './components/AppHeader.vue'
import AppLoading from './components/AppLoading.vue'
import CardsList from './components/CardsList.vue'
import AppSearch from './components/AppSearch.vue'

export default {
  components: {
    AppHeader,
    CardsList,
    AppLoading,
    AppSearch,
  },
  data() {
    return {
      cardsArray: [],
      isLoading: false,
      store,
    }
  },
  created() {
    this.isLoading = true;
    console.log(this.isLoading);
    axios
      .get('https://rickandmortyapi.com/api/character')
      .then((resp) => {
        // salvo l'oggetto della chiamata API nell'array
        this.cardsArray = resp.data.results;
        console.log(this.cardsArray);
        // riporto lo status di isLoading a false
        this.isLoading = false;
        console.log(this.isLoading);

      });
  },
}
</script>

<template>

  <AppHeader />
  <AppSearch />
  <AppLoading v-if="isLoading" />
  <CardsList v-else :cardsArray="cardsArray" />

</template>

<style lang="scss">
body {
  background-color: lightblue;
}
</style>