<template>
    <button class="button is-primary" @click="adicionarTarefa">Adicionar Tarefa</button>
  </template>
  
  <script>
  export default {
    name: 'BotaoAddComponent',
    methods: {
      adicionarTarefa() {
        this.$emit('adicionar-tarefa');
      }
    }
  }
  </script>
  