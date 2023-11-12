<script setup>
import { ref } from 'vue'
import { useTodoListStore } from '@/stores/useTodoListStore'

const todo = ref('')
const store = useTodoListStore()

function addItemAndClear(item) {
  if (item.length === 0) {
    return
  }
  // invokes function in the store:
  store.addTodo(item)
  todo.value = ''
}
</script>

<template>
  <div class="form-container">
    <form @submit.prevent="addItemAndClear(todo)" class="add-form">
      <input v-model="todo" type="text" placeholder="Add new task" class="input-field"/>
      <button type="submit" class="add-button">Add</button>
    </form>
  </div>
</template>

<style scoped>
.form-container {
  text-align: center;
  margin-bottom: 20px;
}

.add-form {
  display: inline-flex;
  width: 80%;
  align-items: center;
  justify-content: space-between;
}

.input-field {
  width: 70%;
  padding: 10px;
  border: 2px solid #ccc;
  border-radius: 5px;
  font-size: 1rem;
}

.add-button {
  background-color: #4caf50;
  color: white;
  border: none;
  padding: 10px 15px;
  border-radius: 5px;
  cursor: pointer;
  font-weight: 600;
  font-size: 1rem;
  transition: background-color 0.3s ease;
}

.add-button:hover {
  background-color: #45a049;
}
</style>