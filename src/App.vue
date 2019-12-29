<template>
  <div id="app">
    <AddTodo
      v-on:add-todo="addTodo"
     />
    <hr>
    <ListTodo 
      v-bind:todos="todos"
    />
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
  },
  methods: {
    addTodo(task) {
      this.todos.push(task);
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  width: 600px;
  margin: 0 auto;
  margin-top: 60px;
}
</style>
