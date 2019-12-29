<template>
  <ul class="list-todo">
    <ListItem 
      v-for="(todo, index) in todos"
      v-bind:key="todo.id"
      v-bind:todo="todo"
      v-bind:index="index"
      v-on:deleteTask="deleteTask"
    />
  </ul>
</template>

<script>
import ListItem from "@/components/ListItem"

export default {
  props: ["todos"],
  components: {
    ListItem
  },
  methods: {
    deleteTask(id) {
      this.$emit("deleteTask", id);
    }
  }
}
</script>

<style scoped>
  .list-todo {
    list-style: none;
    margin: 0;
    padding: 0;
  }
</style>