<template>
    <div>
      <h2>Toutes les tâches</h2>
      <ul>
        <task-item v-for="task in tasks" :key="task.id" :task="task" @delete-task="deleteTask(task.id)"></task-item>
      </ul>
    </div>
  </template>
  
  <script>
  import TaskItem from './TaskItem.vue';
  
  export default {
    components: {
      TaskItem,
    },
    props: {
      tasks: Array,
    },
    methods: {
      deleteTask(taskId) {
        this.$emit('delete-task', taskId);
      },
    },
  };
  </script>
  