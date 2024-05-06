<script>
import axios from 'axios';
export default {
  data() {
    return {

    }
  },
  created() {
    axios
      .get('https://rickandmortyapi.com/api/character')
      .then((resp) => {
        console.log(resp);
      });
  },
}
</script>

<template>
  <h1>CIAO</h1>
</template>

<style lang="scss"></style>