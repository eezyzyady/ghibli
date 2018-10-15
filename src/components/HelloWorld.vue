<template>
  <div>
    <h5>
    <h1><a>Lista de Peliculas</a></h1>
    <h3> Ordenar Peliculas por :
      
      <button @click="filmsPorA"> Año</button>
      <button @click="sortLowest"> Rating</button></h3>
    
     <section class="section">
    <div class="danger">

      <h1 class="has-text-primary	">GHIBLI</h1>
      <h2 class="subtitle">
         <strong><li v-for="film in films" :key="film.title">
      <router-link :to="{name: 'detalle', params: { filmDescription: film.description, filmTitle: film.title, filmDirector: film.director,
      filmProductor: film.producer, filmAnio: film.release_date, filmRT: film.rt_score}}">
        
        <br> {{ film.title }} <br> </router-link>      -by "{{film.director}}" ({{film.release_date}})<h6>Rating: {{ film.rt_score}} </h6>
  
    </li></strong>
      </h2>
    </div>
  </section>

  
    
        </h5>
    
    </div>

    


  
</template>

<script>

import axios from 'axios'

export default {
 name: 'HelloWorld',
  data () {
    return {
      films: []
    }
  },
  mounted () {
    var comp = this
    var apiUrl = 'https://ghibliapi.herokuapp.com/films'
    
  var promise = axios.get(apiUrl)
            promise.then(function(datos){
   console.log(datos)
  comp.films = datos.data
  }, function(error){
    console.log(error)
    var film = promise
    film.sort()
  })
  },
computed: { filmsPorA() { 
  return this.films.sort((a, b) => b.release_date - a.release_date),


  { filmsPorA() {
    return this.films.sort((a,b) => b.rt_score - a.rt_score)
  }
  }
}

},






methods: {

     sortLowest() {console.log('estoy aca')
       this.films.sort(function(a, b) {
   var nameA = a.rt_score.toUpperCase(); // ignore upper and lowercase
   var nameB = b.rt_score.toUpperCase(); // ignore upper and lowercase
  if (nameA < nameB) {
     return -1;
   }
   if (nameA > nameB) {
     return 1;
   }

   // names must be equal
   return 0;
 });

     }
  
}
}

  </script>

<style scoped>
h2 {
  font-weight: normal;
  color: rgb(3, 3, 3);
}

h1 {font-weight: 40px;
color:black;


}

h6 {font-weight: 10px;
color:black;}

ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin:  40px;
  grid-column-end: inherit;
  background-color: blanchedalmond;
  border:white 10px groove;
  border-collapse: collapse;
  
    
  
}
a {
  color: rgb(85, 84, 84);
  opacity: initial;
  opacity: 80%;
  background-clip: content-box;
  background-color: rgb(180, 238, 189);
  border-radius: 50%;
    width: 200px;
    height: 200px; 
}

h5 { background-image: url("https://orig00.deviantart.net/86a7/f/2011/115/a/1/studio_ghibli_business_card_by_pandamonium_123-d3eus4l.jpg"); 
background-position: center;
background-repeat: no-repeat;
background-attachment: fixed;
background-size: cover;
background-blend-mode:lighten;
height: 10%;
-webkit-filter: contrast(100%);
filter: contrast(100%);
opacity: 1;
background-image: 10%;
background-repeat: space;

}


</style>
