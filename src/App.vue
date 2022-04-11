<template>
  <div id="app">
    <AppHeader />
    <RecordList :url="dataUrl" />
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
  data() {
    return {
      dataUrl: "https://flynn.boolean.careers/exercises/api/array/music",
    };
  },
};
</script>

<style lang="scss">
@import "@/style/general";
</style>
