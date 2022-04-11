<template>
  <header>
    <img src="@/assets/spotify-logo.png" alt="Spotyfy Logo" />
  </header>
</template>

<script>
export default {
  name: "AppHeader",
  props: {},
};
</script>

<style lang="scss" scoped>
@import "@/style/variables";

header {
  background-color: $main-color;
  img {
    width: 5rem;
    padding: 10px;
  }
}
</style>
