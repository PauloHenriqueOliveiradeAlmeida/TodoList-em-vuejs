<template>
  <div id="app">
    <md-toolbar :md-elevation="1" class="toolbar">
      <span class="md-title">Lista Todo em Vue</span>
    </md-toolbar>
    <img alt="Vue logo" src="./assets/logo.png" width="25%" />
    <todo />
  </div>
</template>

<script>
import todo from "./components/todo";

export default {
  name: "App",
  components: {
    todo,
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
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  margin: auto;
}
.toolbar {
  margin-bottom: 50px;
}
</style>
