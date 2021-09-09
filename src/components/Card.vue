<template>
  <div class="card p-2">
    <img :src="card.poster" :alt="card.title" />
    <h6 class="m-0">{{ card.title }}</h6>
    <br />
    <div class="info">
      <p class="m-0">{{ card.author }}</p>
      <time>{{ card.year }}</time>
    </div>
  </div>
</template>

<script>
export default {
  name: "Card",
  data() {
    return {};
  },
  props: ["card"],
};
</script>

<style scoped lang="scss">
@import "../assets/scss/_variables.scss";

.card {
  background-color: $card-color;
  height: 300px;
}
</style>