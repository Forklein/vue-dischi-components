<template>
  <main>
    <div class="container my-5">
      <div class="row mx-auto g-3">
        <div v-for="(card, index) in cards" :key="index" class="col-2">
          <Card :card="card" />
        </div>
      </div>
    </div>
  </main>
</template>

<script>
import axios from "axios";
import Card from "@/components/Card.vue";

export default {
  name: "Main",
  components: {
    Card,
  },
  data() {
    return {
      cards: [],
    };
  },
  computed: {
    filteredCards() {
      console.log(this.genre);
      //   return this.cards.filter((card) => {
      //     if (card.genre.includes(this.genre)) {
      //       return true;
      //     }
      //   });
    },
  },
  props: ["genre"],
  created() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((res) => {
        this.cards = res.data.response;
        this.$emit("card", this.cards);
      })
      .catch((err) => {
        console.log(err);
      });
  },
};
</script>

<style scoped lang="scss">
</style>