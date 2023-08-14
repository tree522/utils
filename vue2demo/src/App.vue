<template>
  <div id="app">
    <HelloWorld msg="Welcome to Your Vue.js App" />
    <ColorfulButton></ColorfulButton>
  </div>
</template>

<script>
import HelloWorld from "./components/ArrayUtils1.vue";
import ColorfulButton from "./components/ColorfulButton.vue";
export default {
  name: "App",
  components: {
    HelloWorld,
    ColorfulButton,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
