<template>
    <div id="app"> </div>
    <!-- Aquí meto los componentes de la web-->
    <Navigation />
    
</template>

<script>
// aquí importo toods los componentes que se van a utilizar

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