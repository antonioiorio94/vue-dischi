<template>
  <div class="container">
    <div class="row">
      <div class="col-12 col-md-6 col-xl-3">
        <RecordItem :record="records" />
      </div>
    </div>
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

import axios from "axios";
import RecordItem from "@/components/RecordItem.vue";

export default {
  name: "RecordList",
  data() {
    return {
      records: Object,
    };
  },
  props: {
    url: String,
  },
  components: {
    RecordItem,
  },
  mounted() {
    this.loadData();
  },
  methods: {
    loadData() {
      axios
        .get(this.url)
        .then((response) => {
          if (response.status === 200) {
            this.records = response.data;
            console.log(this.records);
          }
        })
        .catch((error) => {
          console.log(error);
        });
    },
  },
};
</script>

<style lang="scss" scoped></style>
