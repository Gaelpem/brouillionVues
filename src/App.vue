<template>
  <form @submit.prevent="submitFormulaire">
  <label for="nom">Nom:</label>
  <input type="text" id="nom" v-model="nom" placeholder="Nom">
  <label for="age">Age:</label>
  <input type="text" id="age" v-model="age" placeholder="Age">
  </form>
  <p>{{ description }}</p>
</template>

<script>
    export default{
      data(){
        return{
          nom:'',
          age:''
        }
      }, 
      computed:{
          description(){
             return `Nom : ${this.nom.toUpperCase()} , Age: ${this.age}`
          }
      }, 
      methods:{
        submitFormulaire(){
          alert(this.description)
        }
      }
    }
</script>
<style scoped>


</style>