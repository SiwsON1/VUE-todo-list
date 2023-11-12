<script setup>
import TodoApp from './components/todoApp.vue'
</script>

<template>
  <todo-app />
</template>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

#app {
  background-color: #2d3436;
  display: flex;
  justify-content: center;
  align-items: center;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2d3436;
  padding: 20px;
  min-height: 100vh;
}

@media (max-width: 600px) {
  #app {
    flex-direction: column;
    padding: 10px;
  }
}
</style>