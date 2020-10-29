<template>
  <div id="app">
    <SearchBar @termChange="onTermChange"></SearchBar>
  </div>
</template>

<script>
import axios from "axios";
import SearchBar from "./components/SearchBar";
const youtube = process.env.VUE_APP_API_KEY;
export default {
  name: "App",
  components: {
    SearchBar,
  },
  methods: {
    onTermChange(searchTerm) {
      axios
        .get("https://www.googleapis.com/youtube/v3/search", {
          params: {
            key: youtube,
            type: "video",
            part: "snippet",
            q: searchTerm,
          },
        })
        .then((response) => console.log(response));
    },
  },
};
</script>
