<template>
  <div id="app">
    <Header :cardEmit="cards" />
    <Main @card="getCard" />
  </div>
</template>

<script>
import Header from "@/components/Header.vue";
import Main from "@/components/Main.vue";

export default {
  name: "App",
  data() {
    return {
      cards: [],
    };
  },
  components: {
    Header,
    Main,
  },
  methods: {
    getCard(card) {
      this.cards = card;
    },
  },
};
</script>

<style lang="scss">
@import "assets/scss/style.scss";
</style>
