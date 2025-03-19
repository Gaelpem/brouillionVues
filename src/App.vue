<template>
  <form action="" @submit.prevent="addTodo">


    <fieldset role="group">

      <input v-model="newTodo"
      type="text" placeholder="Tache à effectuer">

      <button :disabled="newTodo.length == 0" >Ajouter</button>

    </fieldset>
  </form>


  <div v-if="todos.length == 0">Vous avez pas de tâches à faire </div>

  <div v-else>

    <ul>
      <li v-for="todo in todos" :key="todo.date" :class="{completed: todo.completed}">
      <label>
        <input type="checkbox" :checked="todo.completed" v-model="todo.completed">
        {{ todo.title }}
      </label>
      </li>
    </ul>
   <Checkbox label="Bonjour"/>
  </div>


  
</template>


<script setup>
import { ref } from 'vue';
import Checkbox from './Checkbox.vue'

const newTodo = ref('')

const todos = ref([{
  title: 'Tâche de test', 
  completed: true, 
  date:1
},{
  title: 'Tâche à faire ', 
  completed: false, 
  date:2
}])

const addTodo = () =>{

  todos.value.push({
    title : newTodo.value,
    completed: false,
    date: Date.now()

  })

const sortedTodos = () =>{
  z
}
}
</script>


<style>
.completed{
  opacity: 0.5;
  text-decoration: line-through;
}
</style>