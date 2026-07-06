<script setup>
import { inject } from 'vue';

defineProps(["task", "index"])
const deleteTask = inject("deleteTask");
const toggleStatus = inject("toggleStatus");
</script>

<template>
  <li class="task-item">
    <span :class="{completed : task.completed}" @click="toggleStatus(index)">
       {{ task.title }}</span>
    <button @click="deleteTask(index)">Delete</button>
  </li>

</template>

<style>
.task-item {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 8px;
  background: white;
  margin: 5px 0;
  border-radius: 5px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
}

.task-item span {
  cursor: pointer;
}

.task-item span.completed {
  text-decoration: line-through;
  color: rgb(139, 10, 10);
}

.task-item button {
  background: #dc3545;
  color: white;
  border: none;
  padding: 5px;
  cursor: pointer;
  border-radius: 5px;
}

.task-item button:hover {
  background: #c82333;
}
</style>
