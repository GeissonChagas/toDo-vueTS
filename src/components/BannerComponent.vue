<template>
    <header class="hero is-primary is-fullheight">
      <div class="hero-body">
        <div class="container">
          <h1 class="title">
            To do Vue-TS
          </h1>
          <button class="button is-light" @click="alterarTema">
            <span class="icon">
              <i class="fas fa-adjust"></i>
            </span>
            <span>{{ textoBotao }}</span>
          </button>
        </div>
      </div>
    </header>
  </template>
  
  <script lang="ts">
  import { defineComponent } from 'vue';
  
  export default defineComponent({
    name: 'Banner-Component',
    emits: ['aoTemaAlterado'],
    data() {
      return {
        modoEscuroAtivo: false,
      };
    },
    computed: {
      textoBotao() {
        if (this.modoEscuroAtivo) {
          return 'Desativar modo escuro';
        }
        return 'Ativar modo escuro';
      },
    },
    methods: {
      alterarTema() {
        this.modoEscuroAtivo = !this.modoEscuroAtivo;
        this.$emit('aoTemaAlterado', this.modoEscuroAtivo);
      },
    },
  });
  </script>
  
  <style scoped>
  .hero {
    background-color: #0d3b66;
  }
  
  .title {
    margin-bottom: 1.5rem;
  }
  
  .icon {
    margin-right: 0.5rem;
  }
  </style>
  
  


  
