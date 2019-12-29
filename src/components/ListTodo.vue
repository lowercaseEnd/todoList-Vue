<template>
  <ul class="list-todo">
    <ListItem 
      v-for="todo in todos"
      v-bind:key="todo.id"
      v-bind:todo="todo"
    />
  </ul>
</template>

<script>
import ListItem from "@/components/ListItem"

export default {
  props: ["todos"],
  components: {
    ListItem
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