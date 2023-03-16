<template>
    <header>
        <h1 class="logo">ToDo VueTS</h1>
    </header>
</template>

<script lang="ts"> // linguaguem TypeScript

import { defineComponent } from 'vue';

export default defineComponent({
    name: 'BannerComponent'
})
</script>

<style scoped> /* Estilo do componente (scoped) */
    header{
        background: #0d3b66;
        width: 100%;
        height: 100vh;
    }

    .logo{
        width: 100%;
        height: 200px;
        color: #fff;
        padding: 1rem;
        font-weight: 700;
    }

    @media only screen and (max-width: 768px) {
        header{
            padding: 2.5rem;
            height: auto;
        }
        
    }
</style>

