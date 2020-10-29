<template>
  <div id="app">
    <SearchBar @termChange="onTermChange"></SearchBar>
  </div>
</template>

<script>
import SearchBar from "./components/SearchBar";
export default {
  name: "App",
  components: {
    SearchBar,
  },
  methods: {
    onTermChange() {},
  },
};
</script>