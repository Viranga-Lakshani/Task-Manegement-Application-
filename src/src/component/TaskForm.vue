<template>
  <form @submit.prevent="submitTask" class="task-form">
    <input type="text" v-model="newTask" placeholder="Enter a task" class="task-input">
    <button type="submit" class="add-button">Add Task</button>
  </form>
</template>

<script>
export default {
  name: 'TaskForm',
  data() {
    return {
      newTask: '',
    };
  },
  methods: {
    submitTask() {
      if (this.newTask.trim() !== '') {
        this.$emit('task-added', this.newTask.trim());
        this.newTask = '';
      }
    },
  },
};
</script>
