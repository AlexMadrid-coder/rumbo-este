<template>
    <div id="app">
      <!-- Aquí meto los componentes de la web-->
      <Navigation />
      
    </div>
    
</template>

<script>
// aquí importo toods los componentes que se van a utilizar
import Navigation from './components/layout/navigation.vue';

export default {
  name: 'App',
  // aquí añadimos toodos los compoentntes importados
  components: {
    Navigation
  }
}

</script>

<style>
@import './assets/styles/styles.css';
@import './assets/styles/components.css';
</style>