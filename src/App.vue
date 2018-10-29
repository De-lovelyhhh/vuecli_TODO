<template>
  <div id="app">
    <h1>My Todo</h1>
    <todoInput/>
  </div>
</template>

<script>
import todoInput from './components/todoInput.vue'
export default {
  name: 'App',
  components: {
    todoInput
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
