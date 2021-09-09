<template>
  <header>
    <div class="container">
      <div class="row py-3">
        <div class="col-6">
          <img src="@/assets/img/logo.svg" alt="logo" style="max-width: 50%" />
        </div>
        <div class="col-6 d-flex justify-content-center align-items-center">
          <select
            @change="getSearch"
            v-model.trim="genreSearch"
            :result="genreSearch"
          >
            <option>All</option>
            <option v-for="(gen, index) in filterCardEmit" :key="index">
              {{ gen }}
            </option>
          </select>
        </div>
      </div>
    </div>
  </header>
</template>
<script>
export default {
  name: "Header",
  data() {
    return {
      genreSearch: "All",
    };
  },
  computed: {
    filterCardEmit() {
      const genre = [];
      this.cardEmit.forEach((element) => {
        if (!genre.includes(element.genre)) {
          genre.push(element.genre);
        }
      });
      return genre;
    },
  },
  methods: {
    getSearch() {
      this.$emit("genre", this.genreSearch);
    },
  },
  props: ["cardEmit"],
};
</script>

<style scoped lang="scss">
@import "../assets/scss/_variables.scss";

header {
  background-color: $header-color;
}
</style>