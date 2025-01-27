<template>
  <ul class="task-list">
    <li v-for="(task, index) in tasks" :key="index" class="task-item">
      {{ task }}
      <button @click="$emit('task-deleted', index)" class="delete-button">Delete</button>
    </li>
    <li v-if="tasks.length === 0">No tasks yet. Add some!</li>
  </ul>
</template>

<script>
export default {
  name: 'TaskList',
  props: {
    tasks: {
      type: Array,
      required: true,
    },
  },
};
</script>
