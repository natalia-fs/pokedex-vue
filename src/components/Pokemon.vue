<template>
  <div class="pokemon">
    <div class="card">
      
    </div>
    <h2>{{name}}</h2>
  </div>
</template>

<script>
export default {
  name: 'Pokemon',
  props: {
    // msg: String
    id: Number,
    name: String,
    types: Array,
    sprite: String,
    abilities: Array,

  },
  methods:{

  },
  created(){

  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
