<template>
  <div id="app">
    <HelloWorld msg="Welcome to Your Vue.js App" />
    <Test msg="Welcome to Your Vue.js App" />
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import Test from "./components/Test.vue";
export default {
  name: "App",
  components: {
    HelloWorld,
    Test,
  },
};
</script>
