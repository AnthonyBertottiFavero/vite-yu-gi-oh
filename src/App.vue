<script>
import AppHeader from "./components/AppHeader.vue";
import AppSearch from "./components/AppSearch.vue";
import AppCounter from "./components/AppCounter.vue";
import CardList from "./components/CardList.vue";
import axios from "axios";
import { store } from "./store";

export default {
  data() {
    return {
      store,
    };
  },
  components: {
    AppHeader,
    AppSearch,
    AppCounter,
    CardList,
  },
  methods: {
    requestDataFromApi() {
      axios
        .get("https://db.ygoprodeck.com/api/v7/cardinfo.php", {
          params: {
            num: 20,
            offset: 0,
            archetype: this.store.searchArchetype,
          },
        })
        .then((response) => (this.store.cardList = response.data.data));
    },
  },
  created() {
    axios
      // num=indica il numero di carte che voglio, offset=fa riferimento alla pagina
      .get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0")
      .then((response) => (this.store.cardList = response.data.data));

    axios
      .get("https://db.ygoprodeck.com/api/v7/archetypes.php")
      .then((response) => (this.store.archetypeList = response.data));
  },
};
</script>

<template>
  <AppHeader />
  <main>
    <AppSearch @performSearch="requestDataFromApi" />
    <AppCounter />
    <CardList />
  </main>
</template>

<style lang="scss">
@use "./assets/styles/general.scss" as *;

main {
  padding: 1.5rem;
  background-color: darkcyan;
}
</style>
