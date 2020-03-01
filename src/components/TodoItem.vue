<template>
  <div class="tod-item" v-bind:class="{ 'is-complete': todoItem.completed}">
    <input type="checkbox" v-on:change="markComplete">
    <p>{{ todoItem.title }}</p>
    <button class="del" v-on:click="$emit('del-todo', todoItem.id)">x</button>
  </div>
</template>

<script>
  export default {
    name: "TodoItem",
    props: ["todoItem"],
    methods: {
      markComplete() {
        this.todoItem.completed = !this.todoItem.completed;
      }
    }
  }
</script>

<style scoped>
  .tod-item {
    background: chocolate;
    padding: 10px;
    border-bottom: 1px #ccc dotted;
  }
  .is-complete {
    text-decoration: line-through;
  }
  .del {
    background: #ff0000;
    color: #fff;
    border: none;
    padding: 5px 9px;
    border-radius: 50%;
    cursor: pointer;
    float: right;
  }
</style>