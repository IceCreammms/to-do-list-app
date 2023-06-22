<template>
    <li>
      <div>
        <p>{{ task.description }}</p>
        <p>{{ task.startDate }} - {{ task.endDate }}</p>
        <p>Status: {{ task.status }}</p>
        <p>Priority: {{ task.priority }}</p>
        <button @click="deleteTask">Supprimer</button>
      </div>
    </li>
  </template>
  
  <script>
  export default {
    props: {
      task: Object,
    },
    methods: {
      deleteTask() {
        this.$emit('delete-task', this.task.id);
      },
    },
  };
  </script>
  