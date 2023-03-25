<template>
  <BoxComponent>
    <div class="columns">
      <div class="column is-7">{{ tarefa.descricao || 'Tarefa sem descrição' }}</div>
      <div class="column">
        <CronometroComponent :tempoEmSegundos="tarefa.duracaoEmSegundos"/>
      </div>
      <div class="column">
        <button class="button is secundary" id="remove" @click="removerTarefa">Remover</button>
      </div>
    </div>
  </BoxComponent>
</template>

<script lang="ts">
import { defineComponent, PropType } from "vue";
import CronometroComponent from "./CronometroComponent.vue";
import ITarefa from '../Intefaces/ITarefa';
import BoxComponent from './BoxComponent.vue'

export default defineComponent({
  name: "Tarefa-Component",
  components: {
    CronometroComponent,
    BoxComponent
  },
  props: {
    tarefa: {
      type: Object as PropType<ITarefa>,
      required: true
    }
  },
  methods: {
    removerTarefa() {
      this.$emit("removerTarefa", this.tarefa);
    }
  }
});
</script>

<style scoped>
  #remove{
    color: red;
  }

  #remove:hover{
    background: rgb(255, 111, 111);
    color: white;
    transition: 1s;
  }
</style>
