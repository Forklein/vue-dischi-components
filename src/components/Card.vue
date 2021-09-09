<template>
  <div class="card p-2">
    <img :src="card.poster" :alt="card.title" />
    <br />
    <div class="info text-center">
      <h6>{{ card.title }}</h6>
      <p class="m-0">{{ card.author }}</p>
      <time>{{ card.year }}</time>
    </div>
  </div>
</template>

<script>
export default {
  name: "Card",
  props: ["card"],
};
</script>

<style scoped lang="scss">
@import "../assets/scss/_variables.scss";

.card {
  background-color: $card-color;
  min-height: 350px;
}
</style>