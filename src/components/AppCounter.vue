<script>
import { store } from "../store";

export default {
  data() {
    return {
      store,
    };
  },
};
</script>

<template>
  <div class="container-small">
    <div class="card-number">
      <span class="found-cards">Found {{ store.cardList.length }} Cards</span>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.card-number {
  background-color: black;
  padding: 1.5rem;
  margin-top: 1rem;
  .found-cards {
    color: white;
    font-size: 1.2rem;
    font-weight: 700;
  }
}
</style>
