<template>
  <div id="app">
    <headerBox nameBox="HeadeR" />
    <HelloWorld msg="body" />
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue';
import headerBox from './components/header.vue';

export default {
  name: 'App',
  components: {
    HelloWorld,
    headerBox,
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
  margin: 0;
  padding: 0;
}
</style>
