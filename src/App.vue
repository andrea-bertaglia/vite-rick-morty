<script>
import axios from 'axios';
import AppHeader from './components/AppHeader.vue'
import AppLoading from './components/AppLoading.vue'
import CardsList from './components/CardsList.vue'

export default {
  components: {
    AppHeader,
    CardsList,
    AppLoading
  },
  data() {
    return {
      cardsArray: [],
      isLoading: true
    }
  },
  created() {
    console.log(this.isLoading);
    axios
      .get('https://rickandmortyapi.com/api/character')
      .then((resp) => {
        // console.log(resp);
        // salvo l'oggetto della chiamata API nell'array
        this.cardsArray = resp.data.results;
        console.log(this.cardsArray);
        this.isLoading = false;
        console.log(this.isLoading);

      });
  },
}
</script>

<template>

  <AppHeader />
  <AppLoading :isLoading="isLoading" />
  <CardsList :isLoading="!isLoading" :cardsArray="cardsArray" />

</template>

<style lang="scss">
body {
  background-color: lightblue;
}
</style>