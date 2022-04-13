<template>
  <div class="container mt-3">
    <div class="col-12">
      <SearchComponent @search="filterByName" />
    </div>
    <div v-if="records.length > 0" class="row justify-content-between">
      <RecordItem
        class="col-12 col-md-4 col-xl-2"
        v-for="item in filteredList"
        :key="item.id"
        :record="item"
      />
    </div>
  </div>
</template>

<script>
import axios from "axios";
import RecordItem from "@/components/RecordItem.vue";
import SearchComponent from "@/components/SearchComponent.vue";

export default {
  name: "RecordList",
  data() {
    return {
      records: [],
      searchedText: "",
    };
  },
  props: {
    url: String,
  },
  computed: {
    filteredList() {
      if (this.searchedText === 0) {
        return this.records;
      }
      return this.records.filter(
        (item) =>
          item.author.toLowerCase().includes(this.searchedText.toLowerCase()) ||
          item.title.toLowerCase().includes(this.searchedText.toLowerCase())
      );
    },
  },
  components: {
    RecordItem,
    SearchComponent,
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
    filterByName(searchedText) {
      console.log(searchedText);
      this.searchedText = searchedText;
    },
  },
};
</script>

<style lang="scss" scoped></style>
