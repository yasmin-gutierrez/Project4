<script setup>
import { ref } from 'vue';

const newTask = ref('');
const emit = defineEmits(['add-task']);

const addNewTask = () => {
  if (newTask.value.trim()) {
    emit('add-task', newTask.value);
    newTask.value = '';
  }
};
</script>

<template>
  <div>
    <input v-model="newTask" placeholder="New task" @keyup.enter="addNewTask" />
    <button @click="addNewTask">Add Task</button>
  </div>
</template>

