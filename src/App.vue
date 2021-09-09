<template>
  <div id="app">
    <Header @genre="getSearch" :cardEmit="cards" />
    <Main @card="getCard" :genre="genre" />
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
      genre: "",
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
    getSearch(search) {
      this.genre = search;
    },
  },
};
</script>

<style lang="scss">
@import "assets/scss/style.scss";
</style>
