<template>
  <header>
    <div class="container">
      <div class="row py-3">
        <div class="col-6">
          <img src="@/assets/img/logo.svg" alt="logo" style="max-width: 50%" />
        </div>
        <div class="col-6 d-flex justify-content-center align-items-center">
          <select>
            <option selected disabled>Seleziona un Genere</option>
            <option></option>
          </select>
        </div>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: "Header",
};
</script>

<style scoped lang="scss">
@import "../assets/scss/_variables.scss";

header {
  background-color: $header-color;
}
</style>