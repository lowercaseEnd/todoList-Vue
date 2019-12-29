<template>
  <div id="app">
    <ListTodo />
  </div>
</template>

<script>
import ListTodo from "@/components/ListTodo";

export default {
  name: 'app',
  components: {
    ListTodo    
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
