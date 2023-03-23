<template>
  <div id="app">
    <HelloWorld msg="Welcome to Your Vue.js App" />
    <TestGit msg="Welcome to Your Vue.js App" />
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import TestGit from "./components/TestGit.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
    TestGit,
  },
};
</script>
