<template>
    <div>
        <h1>Detalle De Pelicula </h1>
         <h1>{{$route.params.filmTitle}}</h1>
        <p>{{$route.params.filmDescription}} </p>
        <p>Director: {{$route.params.filmDirector}}</p>
        <p>Productor: {{$route.params.filmProductor}}</p>
        <p>Año: {{$route.params.filmAnio}}</p>
        <p>Rating: {{$route.params.filmRT}}</p>
    
        
       
        <div v-if="film !== null"> 
        
            
        </div>
<div> <router-link :to="{name: 'HelloWorld'}">Volver  </router-link></div>
    </div>
</template>

<script>

import axios from 'axios'

export default {
data () {
     return{
         film: null,
     }
},


 //   mounted () {
 //       var idFilm = this.$route.params.idFilm
 //       var personasURL = "https://ghibliapi.herokuapp.com/people"
 //       console.log(personasURL)
// film.datosPersonajes= []
// var comp = this
//           var personas = axios.get(personasURL)
//   personas.then(function(datos){
//     console.log(datos)
//     comp.film.datosPersonajes = datos.data
//     },
//     function(error){
//       console.log(error)
    
//   })
  //  }

}
</script>

<style>

</style>
