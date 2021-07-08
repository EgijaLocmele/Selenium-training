<template>
  <tabs :data="data"/>
</template>

<script>
import data from "./data/data.json";
import Tabs from "./components/Tabs.vue";

export default {
  name: "App",
  components: {
    Tabs
  },
  data() {
    return {
      data
    };
  }
};
</script>

<style lang="scss">
body {
  margin: 0;
  cursor: default;
  overflow-x: hidden;
  background-color: $darkRed;
  text-align: center;
}
</style>