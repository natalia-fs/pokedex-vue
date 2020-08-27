<template>
  <div class="set">
    <Pokemon v-for="pokemon in pokemons"
      :key="pokemon.id"
      :id="pokemon.id"
      :name="pokemon.name"
      :sprite="pokemon.sprites.front_default"
      :types="pokemon.types"
      :abilities="pokemon.abilities"
    />
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
    pokemons_number: Number,
    start: Number,
    end: Number,
  },
  data(){
    return {
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
          poke_list.push(data)
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
  width: 95vw;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  grid-gap: 1rem;
  margin: 0 auto;
}
</style>
