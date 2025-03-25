<template>
  <form @submit.prevent="addItem">
    <p>What do you need ?</p>
    <input v-model="addFruit" placeholder="Choisissez un fruit" >
    <p>How much you need</p>
    <input type="number" v-model="addNumber" placeholder="Un nombre" >
    <button type="submit">Ajouter</button>
  </form>
  <button @click="deleteItem">Supprimer</button>
  <ul>
    <li v-for="(item , index) in shoppingList" :key ='index'>
  {{ item.name}}, {{ item.number}} </li>
  </ul>
</template>
 
<script>
export default{
  data(){
    return{
      addFruit:'',
      addNumber:'', 
      shoppingList: []
    }
  }, 
  methods:{
    addItem(){
    if(this.addFruit && this.addNumber){
      let item = {
        name: this.addFruit,
        number: this.addNumber
      }
      this.shoppingList.push(item)
      this.addFruit = ''
      this.addNumber = ''

        }
    
    },
    deleteItem(){
      if(this.shoppingList.length > 0){
        this.shoppingList.pop()
      }
    }
  }
}
</script>