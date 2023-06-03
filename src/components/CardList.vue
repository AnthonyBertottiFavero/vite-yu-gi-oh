<script>
import Card from "./Card.vue";
import { store } from "../store";

export default {
  data() {
    return {
      store,
    };
  },
  components: {
    Card,
  },
};
</script>

<template>
  <div class="container-small">
    <div class="card-list">
      <Card v-for="cards in store.cardList" :key="cards.id" :cardData="cards" />
    </div>
  </div>
</template>

<style lang="scss" scoped>
.card-list {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
  background-color: azure;
  margin-top: 1rem;
}
</style>
