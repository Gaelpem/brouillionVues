<template>
  <p>Compteur : {{ count }} </p>


  <button v-on:click="increment">Incrementer</button>
  <button v-on:click="decrement">Decrementer</button>

<ul>
  <li v-for="movie in movies">
    {{ movie }} <button @click="deleteMovie(movie)">Supprimer</button>

  </li>
</ul>
</template>


<script setup>
import { ref } from 'vue';

  const count = ref(1)

  const movies = ref([
    'Lapin',
    'Blanc', 
    'Voisin'
  ]);
  const increment = ()=>{
    count.value++
  }

  const decrement = () =>{
    count.value--
  }

const deleteMovie = (movie) =>{
  movies.value = movies.value.filter(m => m !== movie)
}
</script>

<style>
.active{
  color : red; 
}
</style>
