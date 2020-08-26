<template>
  <div class="set">
    <Pokemon v-for="pokemon in pokemons"
      :key="pokemon.id"
      :id="pokemon.id"
      :name="pokemon.name"
      :sprite="pokemon.sprites.front_deafult"
      :types="pokemon.types"
      :abilities="pokemon.abilities"
    >
    </Pokemon>
  </div>
</template>

<script>
import Pokemon from './Pokemon.vue'
export default {
  name: 'Pokemons',
  components:{
    Pokemon
  },
  props: {
 
  },
  data(){
    return {
      pokemons_number: 150,
      base_url: 'https://pokeapi.co/api/v2/pokemon/',
      pokemons: []
    }
  },
  methods:{
    async fetchPokemons(){
      let poke_list = [];
      for(let i=1; i<=this.pokemons_number; i++){
        let request = new Request(`${this.base_url}${i}`);
        
        fetch(request).then((response, error) => {
          if(response.status === 200) return response.json()
          else console.log(error);
        })
        .then((data) => {
          console.log(data)
          poke_list.push(data)
          console.log(poke_list.length)
        })
      }
      this.pokemons = poke_list;
    },


  },
  beforeMount(){
    this.fetchPokemons();
  },
}
</script>
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.set{
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  align-items: center;
  justify-content: center;
  
}
</style>
