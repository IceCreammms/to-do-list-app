<template>
  <div>
    <h1>Ma liste de tâches</h1>
    <task-form @add-task="addTask"></task-form>
    <task-list :tasks="tasks" @delete-task="deleteTask"></task-list>
  </div>
</template>

<script>
import TaskForm from './components/TaskForm.vue';
import TaskList from './components/TaskList.vue';

export default {
  components: {
    TaskForm,
    TaskList,
  },
  data() {
    return {
      tasks: [],
    };
  },
  methods: {
    addTask(task) {
      task.id = Date.now();
      this.tasks.push(task);
    },
    deleteTask(taskId) {
      this.tasks = this.tasks.filter(task => task.id !== taskId);
    },
  },
};
</script>
