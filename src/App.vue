<template>
  <div id="app">
    <!-- Mostrando componente 'Planetas' no template 'App.vue' -->
    <Planetas/>
  </div>
</template>

<script>
  // Importando componente 'Planetas' 
  import Planetas from './components/Planetas.vue'
   
  export default {
    name: 'App',
    components: {
      Planetas
    }
  }
</script>

<style>
  #app {
    /* */
  }
</style>
