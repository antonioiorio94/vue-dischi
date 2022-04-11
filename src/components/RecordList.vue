<template>
  <div class="container mt-3">
    <div v-if="records.length > 0" class="row justify-content-between">
      <RecordItem
        class="col-12 col-md-4 col-xl-2"
        v-for="item in records"
        :key="item.id"
        :record="item"
      />
    </div>
  </div>
</template>

<script>
import axios from "axios";
import RecordItem from "@/components/RecordItem.vue";

export default {
  name: "RecordList",
  data() {
    return {
      records: [],
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
            this.records = response.data.response;
            console.log(this.records[1]);
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
