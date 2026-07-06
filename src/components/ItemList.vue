<script setup>
import SingleItem from './SingleItem.vue';
defineProps(["tasks"])
</script>

<template>
  <ul class="task-list">
    <SingleItem
    v-for="(task, index) in tasks"
    :key="index"
    :task="task"
    :index="index"
    />
  </ul>
</template>

<style>
.task-list {
  list-style: none;
  padding: 0;
}
</style>
