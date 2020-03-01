<template>
  <div>
    <div v-for="todo in todos" v-bind:key="todo.id">
      <TodoItem v-bind:todoItem="todo" v-on:del-todo="$emit('del-todo', todo.id)" />
    </div>
  </div>
</template>

<script>
  import TodoItem from "./TodoItem";

  export default {
    name: "Todos",
    components: {
      TodoItem
    },
    props: ["todos"],
    data() {
      return {

      }
    }
  }
</script>

<style scoped>

</style>