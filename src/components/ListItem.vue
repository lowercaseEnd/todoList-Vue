<template>
  <li class="list-todo__item">
    <span v-bind:class="{done: todo.completed}">
    <input type="checkbox" class="list-todo__complete" v-on:change="todo.completed = !todo.completed">
    {{todo.task | uppercase}}
    </span>
    <button type="button" class="list-todo__delete" v-on:click="deleteTask">&times;</button>
  </li>
</template>

<script>
export default {
  props: {
    todo: {
      type: Object,
      required: true
    }
  },
  methods: {
    deleteTask() {
      this.$emit("deleteTask", this.todo.id);
    }
  },
  filters: {
    uppercase(value) {
      return value.toUpperCase();
    }
  }
}
</script>

<style scoped>
  .list-todo__item {
    display: flex;
    width: 100%;
    height: 30px;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    border: 1px solid #cccccc;

  }
  .list-todo__delete {
    border: none;
    background-color: red;
    color: white;
    font-weight: bold;
    width: 20px;
    height: 20px;
    border-radius: 50%;
    margin-right: 15px;
  }
  .list-todo__complete {
    margin-left: 15px;
    
  }
  .done {
    text-decoration: line-through;
  }
</style>