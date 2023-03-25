<template>
  <main class="columns is-gapless is-multiline" :class="{ 'modo-escuro': modoEscuroAtivo }">
    <div class="column is-one-quarter">
      <BannerComponent @aoTemaAlterado="trocarTema"/>
    </div>
    <div class="column is-three-quarter conteudo">
      <FormularioComponent @aoSalvarTarefa="salvarTarefa"/>
      <div class="lista">
        <TarefasComponent v-for="(tarefa, index) in tarefas" :key="index" :tarefa="tarefa"/>
        <BoxComponent v-if="listaEstaVazia">
          Você não está muito produtivo hoje :(
        </BoxComponent>
      </div>
    </div>
  </main>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import BannerComponent from './components/BannerComponent.vue'
import FormularioComponent from './components/FormularioComponent.vue'
import TarefasComponent from './components/TarefasComponent.vue'
import BoxComponent from './components/BoxComponent.vue'
import ITarefa from './Intefaces/ITarefa'

export default defineComponent({
  name: 'App',
  components: {
    BannerComponent,
    FormularioComponent,
    TarefasComponent,
    BoxComponent
  },
  data () {
    return {
      tarefas: [] as ITarefa[],
      modoEscuroAtivo: false
    }
  },
  computed: {
    listaEstaVazia () : boolean {
      return this.tarefas.length === 0
    }
  },
  methods: {
    salvarTarefa (tarefa: ITarefa) {
      this.tarefas.push(tarefa)
    },
    trocarTema (modoEscuroAtivo: boolean) {
      this.modoEscuroAtivo = modoEscuroAtivo
    }
  }
});
</script>

<style>
.lista {
  padding: 1.25rem;
}
main {
  --bg-primario: #fff;
  --texto-primario: #000;
}
main.modo-escuro {
  --bg-primario: #2b2d42;
  --texto-primario: #ddd;
}
.conteudo {
  background-color: var(--bg-primario);
}
</style>
