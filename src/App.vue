<template>
  <main class="columns is-gapless is-multiline">
    <div class="column is-one-quarter">
      <BannerComponent />
    </div>
    <div class="column is-three-quarter">
      <div v-for="(componente, index) in componentes" :key="index">
        <component :is="componente"  />
      </div>
      <TarefasComponent />
    </div>
  </main>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import BannerComponent from './components/BannerComponent.vue';
import FormularioComponent from './components/FormularioComponent.vue';
import TarefasComponent from './components/TarefasComponent.vue';

export default defineComponent({
  name: 'App',
  components: {
    BannerComponent,
    FormularioComponent,
    TarefasComponent
  },
  data () {
    return {
      componentes: [FormularioComponent]
    }
  },
  methods: {
    adicionarTarefa() {
      this.componentes.push(FormularioComponent);
      localStorage.setItem('tarefas', JSON.stringify(this.componentes));
    },
    removerTarefa (index: number) {
      this.componentes.splice(index, 1)
      localStorage.setItem('tarefas', JSON.stringify(this.componentes));
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

#remove{
  margin: 1rem;
  background-color: #FF0000;
  color: #FFFFFF;
}
#remove:hover{
  background-color: #FF3333;
}
</style>
