<template>
    <div class="pokemon">
      <div class="card">
        <div class="face preview" :style="'background: var(--'+types[0].type.name+');'">
          <div class="content">
            <h1>{{name}}</h1>
            
            <h3>Type:</h3> {{types[0].type.name}}
            <h3>Abilities:</h3>
            <div v-for="abl in abilities" :key="abl.ability.name" class="abilities">
              <p>{{abl.ability.name}}</p>
            </div>
          </div>
        </div>
        <div class="face info">
          <img :src="`https://pokeres.bastionbot.org/images/pokemon/${id}.png`" :alt="name">
        </div>
      </div>
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
    img: String,
  },
  methods:{

  },
  created(){

  }
}
</script>
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.card{
  position: relative;
  width: 300px;
  height: 400px;
  margin: 0 auto;
  background: #FFF;
  transition: .5s;
  border-radius: .8rem;
}
.card:hover{
  box-shadow: 0 30px 30px rgba(0,0,0,.2);
}
.card .face{
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}

.card .face.preview{
  box-sizing: border-box;
  padding: 20px;
  text-align: center;
  color: #FFF;
  border-radius: .8rem;
}

.card .face.preview h1{
  margin-top: 60px;
}
.card .content{
  min-width: 75%;
  padding: 5%;
  border-radius: .8rem;
  background-image: linear-gradient(180deg, transparent, rgba(0,0,0,.2));
}
.card .face.info{
  background: linear-gradient(black, #777777);
  border-radius: .7rem;
  transition: .5s;
}
.card:hover .face.info{
  height: 100px;
  width: 100px;
  border-radius: 50%;
  top: 20px;
  left: 50%;
  transform: translateX(-50%);
  background: transparent;
}

/* .card .face.info h2{ */
.card .face.info img{
  margin: 0;
  padding: 0;
  color: #FFF;
  transition: .5s;
  max-width: 85%;
}
.card:hover .face.info h1{
  color: darkblue;
  
}

.card h3{
  margin: .5rem 0;
}

</style>
