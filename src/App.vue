<template>
  <main class="columns is-gapless is-multiline">
    <div class="column is-one-quarter">
      <BannerComponent />
    </div>
    <div class="column is-three-quarter">
      <div v-for="(componente, index) in componentes" :key="index">
        <component :is="componente" @adicionar-tarefa="adicionarTarefa" />
      </div>
      <div>
        <button id ="add" class="button is-primary" @click="adicionarTarefa">Adicionar</button>
        <button id ="add" class="button is-secundary" @click="removerTarefa">Remover</button>
      </div>
    </div>
  </main>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import BannerComponent from './components/BannerComponent.vue';
import FormularioComponent from './components/FormularioComponent.vue'

export default defineComponent({
  name: 'App',
  components: {
    BannerComponent,
    FormularioComponent
  },
  data () {
    return {
      componentes: [FormularioComponent]
    }
  },
  methods: {
    adicionarTarefa() {
      this.componentes.push(FormularioComponent);
    },
    removerTarefa (index: number) {
      this.componentes.splice(index, 1)
    }
  }
});
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
#add{
  margin: 1rem;
}
</style>
