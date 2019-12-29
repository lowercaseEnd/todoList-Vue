<template>
  <div id="app">
    <AddTodo
      
     />
    <hr>
    <ListTodo />
  </div>
</template>

<script>
import ListTodo from "@/components/ListTodo";
import AddTodo from "@/components/AddTodo";

export default {
  name: 'app',
  data() {
    return {
      todos: []
    }
  },
  components: {
    ListTodo,
    AddTodo    
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
