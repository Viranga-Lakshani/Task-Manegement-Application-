<template>
  <div class="app-container">
    <h1>Task Manager</h1>
    <TaskForm @task-added="addTask" />
    <TaskList :tasks="tasks" @task-deleted="deleteTask" />
  </div>
</template>

<script>
import TaskList from './components/TaskList.vue';
import TaskForm from './components/TaskForm.vue';

export default {
  name: 'App',
  components: {
    TaskList,
    TaskForm
  },
  data() {
    return {
      tasks: [],
    };
  },
  methods: {
    addTask(newTask) {
      this.tasks.push(newTask);
    },
    deleteTask(index) {
      this.tasks.splice(index, 1);
    },
  },
};
</script>
