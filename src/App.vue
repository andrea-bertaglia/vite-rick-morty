<script>
import axios from 'axios';
import AppHeader from './components/AppHeader.vue'
import CardsList from './components/CardsList.vue'

export default {
  components: {
    AppHeader,
    CardsList,
  },
  data() {
    return {
      cardsArray: [],
    }
  },
  created() {
    axios
      .get('https://rickandmortyapi.com/api/character')
      .then((resp) => {
        // console.log(resp);
        // salvo l'oggetto della chiamata API nell'array
        this.cardsArray = resp.data.results;
        console.log(this.cardsArray);
      });
  },
}
</script>

<template>

  <AppHeader />
  <CardsList :cardsArray="cardsArray" />

</template>

<style lang="scss">
body {
  background-color: lightblue;
}
</style>