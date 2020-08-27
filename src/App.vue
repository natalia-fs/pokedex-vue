<template>
  <div id="app">
    <Pokemons :pokemons_number="60"/>
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
:root{
  --grass: #78c850;
  --fire: #f08030;
  --water: #6890f0;
  --electric: #f8d030;
  --psychic: #f85888;
  --ice: #98d8d8;
  --normal: #a8a878;
  --dragon: #7038f8;
  --dark: #705848;
  --fighting: #c03028;
  --poison: #a040a0;
  --bug: #a8b820;
  --ground: #e0c068;
  --rock: #b8a038;
  --flying: #a890f0;
  --steel: #b8b8d0;
  --ghost: #705898;
  --fairy: #b5949e;
}

*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  outline: none;
}
body{
  padding: 2%;
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  background: #252525;
  font-family: 'Poppins';
  text-transform: capitalize;
}
</style>
