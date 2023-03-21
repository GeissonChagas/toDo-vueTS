<template>
    <div class="column">
        <div
        class="is-flex is-align-items-center is-justify-content-space-between"
        >
        <CronometroComponent :tempoEmSegundos="tempoEmSegundos" />
        <button class="button" @click='iniciar'>
            <span class="icon">
            <i class="fas fa-play"></i>
            </span>
            <span>Play</span>
        </button>
        <button class="button" @click="finalizar">
            <span class="icon">
            <i class="fas fa-stop"></i>
            </span>
            <span>Stop</span>
        </button>
        </div>
    </div>
  </template>

<script lang="ts">
import { defineComponent } from "vue";
import CronometroComponent from "./CronometroComponent.vue";

export default defineComponent({
  name: "FormularioComponent",
  components: {
    CronometroComponent
  },
  data () {
    return {
      tempoEmSegundos: 0,
      cronometro: 0,
      tarefas: [] as { nome: string, tempo: number }[]
    }
  },
  methods: {
    iniciar() {
      this.cronometro = setInterval(() => {
        this.tempoEmSegundos += 1;
      }, 1000);
      console.log("iniciando");
    },
    finalizar() {
      clearInterval(this.cronometro);
    },
    adicionarTarefa() {
      const input = this.$el.querySelector("input");
      const novaTarefa = { nome: input.value, tempo: this.tempoEmSegundos };
      this.tarefas.push(novaTarefa);
      input.value = "";
      this.tempoEmSegundos = 0;
    }
  }
});
</script>
