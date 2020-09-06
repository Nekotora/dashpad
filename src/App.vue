<template>
  <div id="app">
    <h1>Hello Dashpad!</h1>
    <hello-world></hello-world>
    <Clock></Clock>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Clock from './components/Clock.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    Clock
  }
}
</script>

<style>
*{
  padding: 0;
  margin: 0;
}
body {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  background-color: #000;
  color: #fff;
  margin-top: 60px;
}
</style>
