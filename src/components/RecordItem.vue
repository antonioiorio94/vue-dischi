<template>
  <div class="card">
    <img :src="record.poster" :alt="record.title" />
    <h2>{{ record.title }}</h2>
    <p class="mb-0">{{ record.author }}</p>
    <p>{{ record.year }}</p>
  </div>
</template>

<script>
/*
ESEMPIO DATA

author: "Bon Jovi"
genre: "Rock"
poster: "https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg"
title: "New Jersey"
year: "1988"
*/

export default {
  name: "RecordItem",
  props: {
    record: Object,
  },
};
</script>

<style lang="scss" scoped>
@import "@/style/variables";

.card {
  text-align: center;
  background-color: $main-color;
  margin: 0.5rem;
  img {
    padding: 20px;
  }
  h2 {
    color: $title-color;
    font-weight: 700;
  }
  p {
    color: $p-color;
  }
}
</style>
