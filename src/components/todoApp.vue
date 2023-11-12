<script setup>
import TodoForm from './todoForm.vue'
import TodoList from './todoList.vue'
</script>

<template>
  <div class="todo-app">
    <h1 class="header">To Do List</h1>
    <todo-form />
    <todo-list />
  </div>
</template>

<style scoped>
.todo-app {
  padding: 5vh 0;
  min-height: 100vh;
  width: 40vw;
  margin: auto;
  background-color: #f0f4f8;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  border-radius: 8px;
}

.header {
  text-align: center;
  color: #333;
  font-size: 2.5rem;
  margin-bottom: 2vh;
  font-weight: 600;
}
</style>