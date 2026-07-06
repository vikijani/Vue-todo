<script setup>
import { provide, reactive } from 'vue';
import FormSubmit from './components/FormSubmit.vue';
import ItemList from './components/ItemList.vue';

const tasks = reactive([]);

function addTask(task){
  console.log(task)
  tasks.push({title: task, completed: false})
}

function deleteTask(index){
  console.log(index);
  tasks.splice(index, 1)
}

function toggleStatus(index){
  tasks[index].completed = !tasks[index].completed
}

provide("deleteTask", deleteTask);
provide("toggleStatus", toggleStatus);
</script>

<template>
  <div class="app-container">
    <h1>Todo Project</h1>
    <FormSubmit @add-task="addTask"/>
    <ItemList v-bind:tasks="tasks"/>
  </div>
</template>

<style>
body{
  color: #333;
  background-color: #f9f9f9;
}
.app-container {
  max-width: 400px;
  margin: 40px auto;
  background: #f9f9f9;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
  text-align: center;
}
h1 {
  font-size: 24px;
  color: #333;
}
</style>
