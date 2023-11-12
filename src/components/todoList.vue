<script setup>
import { useTodoListStore } from '@/stores/useTodoListStore'
import { storeToRefs } from 'pinia'

const store = useTodoListStore();

// storeToRefs lets todoList keep reactivity:
const { todoList } = storeToRefs(store)

// destructuring action method doesn't require using storeToRefs:
const { toggleCompleted, deleteTodo } = store

</script>

<template>
  <div class="list-container">
    <div v-for="todo in todoList" :key="todo.id" class="list-item">
      <span :class="{ completed: todo.completed }">{{ todo.item }}</span>
      <div class="actions">
        <button @click.stop="toggleCompleted(todo.id)" class="complete-button">&#10004;</button>
        <button @click="deleteTodo(todo.id)" class="delete-button">&#10060;</button>
      </div>
    </div>
  </div>
</template>

<style scoped>
.list-container {
  max-width: 80%;
  margin: auto;
}

.list-item {
  display: flex;
  align-items: center;
  justify-content: space-between;
  background-color: #fff;
  margin-bottom: 10px;
  padding: 10px;
  border-radius: 5px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
  font-size: 1.2rem;
}

.completed {
  text-decoration: line-through;
  color: #777;
}

.actions button {
  border: none;
  background: none;
  cursor: pointer;
  font-size: 1.2rem;
  padding: 5px;
  transition: color 0.3s ease;
}

.complete-button {
  color: #4caf50;
}

.complete-button:hover {
  color: #388e3c;
}

.delete-button {
  color: #f44336;
}

.delete-button:hover {
  color: #d32f2f;
}
</style>