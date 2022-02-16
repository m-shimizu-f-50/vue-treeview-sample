<template>
  <div id="app">
    <v-app>
      <TreeView />
    </v-app>
  </div>
</template>

<script>
import TreeView from "./components/TreeView";
export default {
  name: "App",
  components: {
    TreeView,
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
