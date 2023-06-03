<script>
export default {
  props: {
    cardData: Object,
  },
};
</script>
<template>
  <div class="card">
    <img :src="cardData.card_images[0].image_url" :alt="cardData.name" />
    <h2>{{ cardData.name }}</h2>
    <div class="type">{{ cardData.archetype }}</div>
  </div>
</template>

<style lang="scss" scoped>
.card {
  width: calc((100% - 4rem) / 5);
  border: 1px solid brown;
  background-color: cornsilk;
  img {
    width: 100%;
  }
  h2 {
    font-size: 1rem;
    text-align: center;
    color: cornflowerblue;
  }
  .type {
    text-align: center;
    font-size: 0.9rem;
    padding-top: 0.7rem;
    color: darkblue;
  }
}
</style>
