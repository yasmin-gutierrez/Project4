<script setup>
defineProps(['task']);
const emit = defineEmits(['toggle-task', 'delete-task']);
</script>

<template>
    <div class="list">
        <li :class="{ completed: task.completed }" >
            <span @click="emit('toggle-task', task.id)">{{ task.text }}</span>
            <button class="deleteButton" @click="emit('delete-task', task.id)" >Delete</button>
        </li>
  </div>
</template>
