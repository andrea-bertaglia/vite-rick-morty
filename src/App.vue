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
      isLoading: false,
      store,
    }
  },
  created() {
    this.getCards();
  },
  methods: {
    getCards() {
      this.isLoading = true;
      console.log("get cards", this.store.selectedStatus);

      const paramsObj = {
        status: "",
      };

      if (this.store.selectedStatus !== "All") {
        paramsObj.status = this.store.selectedStatus;
      }
      console.log("status selezionato: ", paramsObj.status);

      axios
        .get('https://rickandmortyapi.com/api/character', {
          params: paramsObj,
        })
        .then((resp) => {
          // salvo l'oggetto della chiamata API 
          this.store.cardsList = resp.data.results;
          console.log(this.store.cardsList);
          // riporto lo status di isLoading a false
          this.isLoading = false;
          console.log("status isLoading", this.isLoading);
        });
    },
  },
}
</script>

<template>

  <AppHeader />
  <AppSearch @filter="getCards" />
  <AppLoading v-if="isLoading" />
  <CardsList v-else :cardsArray="this.store.cardsList" />

</template>

<style lang="scss">
body {
  background-color: lightblue;
}
</style>