<script setup>
import { ref, computed, onMounted, watch } from 'vue';
import TaskList from './components/TaskList.vue';
import TaskForm from './components/TaskForm.vue';

const tasks = ref([]);

const addTask = (taskText) => {
  tasks.value.push({ id: Date.now(), text: taskText, completed: false });
};

const toggleTask = (taskId) => {
  const task = tasks.value.find(t => t.id === taskId);
  if (task) task.completed = !task.completed;
};

const deleteTask = (taskId) => {
  tasks.value = tasks.value.filter(t => t.id !== taskId);
};

const remainingTasks = computed(() => tasks.value.filter(task => !task.completed).length);

</script>

<template>
  <div class="app">
    <div class="container">
       <h1>To Do List</h1>
    <TaskForm @add-task="addTask" />
    <p><strong>Remaining tasks:</strong> {{ remainingTasks }}</p>
    <TaskList :tasks="tasks" @toggle-task="toggleTask" @delete-task="deleteTask" />
    </div>
   
  </div>
</template>


