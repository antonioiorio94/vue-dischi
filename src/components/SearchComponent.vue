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

<style lang="scss" scoped></style>
