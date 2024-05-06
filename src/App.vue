<script>
import axios from 'axios';
export default {
  data() {
    return {
      cardsArray: []
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
  <h1>CIAO</h1>
</template>

<style lang="scss"></style>