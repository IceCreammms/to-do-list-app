<template>
    <form @submit.prevent="addTask">
      <input type="text" v-model="description" placeholder="Description" required>
      <input type="date" v-model="startDate" placeholder="Date de début" required>
      <input type="date" v-model="endDate" placeholder="Date de fin" required>
      <select v-model="status">
        <option value="à faire">À faire</option>
        <option value="en cours">En cours</option>
        <option value="terminé">Terminé</option>
      </select>
      <select v-model="priority">
        <option value="haute">Haute</option>
        <option value="moyenne">Moyenne</option>
        <option value="basse">Basse</option>
      </select>
      <button type="submit">Ajouter</button>
    </form>
  </template>
  
  <script>
  export default {
    data() {
      return {
        description: '',
        startDate: '',
        endDate: '',
        status: 'à faire',
        priority: 'basse',
      };
    },
    methods: {
      addTask() {
        const task = {
          description: this.description,
          startDate: this.startDate,
          endDate: this.endDate,
          status: this.status,
          priority: this.priority,
        };
        this.$emit('add-task', task);
        this.description = '';
        this.startDate = '';
        this.endDate = '';
        this.status = 'à faire';
        this.priority = 'basse';
      },
    },
  };
  </script>
  