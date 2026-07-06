<script setup>
import FormSubmit from './components/FormSubmit.vue';
import ItemList from './components/ItemList.vue';

let tasks = [];

function addTask(task){
  tasks.push({title: task, completed: false})
}

function deleteTask(index){
  tasks.splice(index, 1)
}

function toggleStatus(index){
  tasks[index].completed = !tasks[index].completed
}
</script>

<template>
  <div class="app-container">
    <h1>Todo Project</h1>
    <FormSubmit @add-task="addTask"/>
    <ItemList/>
  </div>
</template>

<style>
body{
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
