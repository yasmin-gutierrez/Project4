<script setup>
import TaskItem from './TaskItem.vue';

defineProps(['tasks']);
const emit = defineEmits(['toggle-task', 'delete-task']);
</script>

<template>
  <ul>
    <TaskItem 
      v-for="task in tasks" 
      :key="task.id" 
      :task="task" 
      @toggle-task="emit('toggle-task', task.id)" 
      @delete-task="emit('delete-task', task.id)" 
    />
  </ul>
</template>