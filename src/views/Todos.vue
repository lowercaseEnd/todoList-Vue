<template>
  <div id="app">
    <h2 class="page-title">App</h2>
    <router-link to="/" class="link">Home</router-link>
    <hr>
    <AddTodo
      v-on:add-todo="addTodo"
     />
     <select v-model="filter" class="filter-todos">
       <option value="all">All</option>
       <option value="completed">Completed</option>
       <option value="not-completed">Not completed</option>
     </select>
    <hr>
    <ListTodo 
      v-bind:todos="filteredTodos"
      v-on:deleteTask="deleteTask"
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
      todos: [],
      filter: "all"
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
  },
  computed: {
    filteredTodos() {
      if (this.filter === "all") {
        return this.todos;
      }
      if (this.filter === "completed") {
        return this.todos.filter(element => element.completed);
      }
      if (this.filter === "not-completed") {
        return this.todos.filter(element => !element.completed);
      }
    }
  }
}
</script>

<style scoped>
  .page-title,
  .link {
    text-align: center;
  }
</style>