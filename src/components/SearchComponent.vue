<template>
  <div>
    <input
      type="text"
      placeholder="Cosa vuoi ascoltare?"
      v-model.trim="inputText"
      @keyup.enter="$emit('search', inputText)"
    />
    <button @click.prevent="performSearch()">Cerca</button>
  </div>
</template>

<script>
export default {
  name: "SearchComponent",
  data() {
    return {
      inputText: "",
    };
  },
  methods: {
    performSearch() {
      console.log(this.inputText);
      this.$emit("search", this.inputText);
    },
  },
};
</script>

<style lang="scss" scoped>
@import "@/style/variables";
input {
  border: none;
  background-color: transparent;
  border-bottom: 2px solid $main-color;
  width: 75rem;
  margin-right: 2rem;
  margin-bottom: 2rem;
}
button {
  border: 2px solid $main-color;
  background-color: transparent;
  border-radius: 20px;
  color: $main-color;
}
</style>
