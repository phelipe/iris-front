<template>
  <div id="app">    
    <HelloWorld/>
      <footer>
  <!-- <a href="https://www.vecteezy.com/free-vector/iris-flower">Iris Flower Vectors by Vecteezy</a> -->
</footer>
  </div>

</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  }
}
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
