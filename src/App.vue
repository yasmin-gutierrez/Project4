<script setup>
import { ref, computed, onMounted, watch } from 'vue';
import TaskList from './components/TaskList.vue';
import TaskForm from './components/TaskForm.vue';


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


