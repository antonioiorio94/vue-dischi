<template>
  <div id="app">
    <AppHeader />
    <RecordList />
  </div>
</template>

<script>
import AppHeader from "@/components/AppHeader.vue";
import RecordList from "@/components/RecordList.vue";

export default {
  name: "App",
  components: {
    AppHeader,
    RecordList,
  },
};
</script>

<style lang="scss">
@import "@/style/general";
</style>
