<template>
  <form v-on:submit.prevent="onSubmit" class="input-form">
    <input type="text" class="input-task" v-model="task">
    <button type="submit" class="add-task">Add a todo</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      task: ""
    }
  },
  methods: {
    onSubmit() {
      if(this.task.trim()) {
        const newTask = {
          id: Date.now(),
          task: this.task,
          completed: false
        };
        this.$emit("add-todo", newTask);
        this.task = ""
      }
    }
  }
}
</script>

<style scoped>
  .input-task {
    width: 490px;
    /* margin: 0 auto; */
  }
  .add-task {
    border: none;
    background-color: #e5e5e5;
    color: #2f2c2c;
    font-size: 18px;
    width: 100px;
    height: 30px;
  }
  .input-form {
    width: 600px;
    margin: 0 auto;
    display: flex;
    justify-content: space-around;
    margin-bottom: 20px;
  }
</style>