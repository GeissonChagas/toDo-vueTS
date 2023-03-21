<template>
  <div class="box">
    <div class="columns">
      <div
        class="column is-8"
        role="form"
        aria-label="Formulário para criar uma tarefa"
      >
        <input
          type="text"
          class="input"
          placeholder="Qual tarefa você deseja iniciar?"
        />
      </div>
      <TemporizadorComponent />
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import TemporizadorComponent from "./TemporizadorComponent.vue";

export default defineComponent({
  name: "FormularioComponent",
  components: {
    TemporizadorComponent
  },
});
</script>


<style scoped>
</style>