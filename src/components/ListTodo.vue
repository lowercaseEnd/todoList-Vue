<template>
  <ul class="list-todo">
    <ListItem />
  </ul>
</template>

<script>
import ListItem from "@/components/ListItem"

export default {
  components: {
    ListItem
  }
}
</script>

<style scoped>
  .list-todo {
    list-style: none;
  }
</style>