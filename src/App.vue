<template>
  <div id="app">
    <h1 class="main-title">Todo app</h1>
    <hr>
    <router-view />
  </div>
</template>

<script>
import ListTodo from "@/components/ListTodo";
import AddTodo from "@/components/AddTodo";

export default {
  name: 'app',
  data() {
    return {
      todos: [],
    }
  },
  components: {
    ListTodo,
    AddTodo    
  },
  methods: {
    addTodo(task) {
      this.todos.push(task);
    },
    deleteTask(id) {
      this.todos = this.todos.filter(element => element.id !== id);
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
.filter-todos {
  display: block;
  margin: 0 auto;
}
.main-title {
  text-align: center;
}
</style>
