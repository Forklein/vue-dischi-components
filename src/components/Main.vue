<template>
  <div class="box">Test</div>
</template>

<script>
import axios from "axios";

export default {
  name: "Main",
  data() {
    return {
      cards: [],
    };
  },
  created() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((res) => {
        console.log(res.data.response);
      })
      .catch((err) => {
        console.log(err);
      });
  },
};
</script>

<style scoped lang="scss">
</style>