<template>
  <div id="app">
    <Pokemons />
  </div>
</template>

<script>
import Pokemons from './components/Pokemons.vue'

export default {
  name: 'App',
  components: {
    Pokemons
  }
}
</script>

<style>
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>
