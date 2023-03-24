<template>
  <div class="box">
    <div class="rows" >
      <div
        class="rows is-8"
        role="form"
        aria-label="Formulário para criar uma tarefa"
      >
        <h3>Tarefa</h3>
        <p> 00:00:00 </p>
      </div>
      <div>
        <button id ="remove" class="button is-secundary" @click="removerTarefa">Remover</button>
      </div>
    </div>
  </div>
</template>

<script>

import { defineComponent } from "vue";
import CronometroComponent from 'vue';

    export default {
        name: 'tarefas-component'
    }

</script>

<style scoped>
    h3{
        font-weight: 700;
        font-size: 20px;
    }
</style>