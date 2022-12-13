<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <FormularioVue></FormularioVue>
    <TablaFormulario></TablaFormulario>
  </div>
</template>

<script>

import FormularioVue from './components/FormularioVue.vue';
import TablaFormulario from './components/TablaFormulario.vue';

export default {
  name: 'App',
  components: {
    FormularioVue,
    TablaFormulario,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
