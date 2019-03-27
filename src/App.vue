<template>
  <div id="app">
    <app-menu />
      <router-view/>
  </div>
</template>

<script>
import AppMenu from './components/AppMenu.vue'

export default {
  components: {
    AppMenu
  }
}
</script>

<style>
html body {
  margin: 0;
  padding: 0;
}

#app {
  font-family: 'Manrope';
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}


</style>
