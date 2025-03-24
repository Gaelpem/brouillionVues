<template>
  <input v-model="recherche" placeholder="Recherche">
  <ul>
    <li v-for="nom in  firlterNom" :key="nom">{{ nom }}</li>
  </ul>
</template>


<script>
export default{
    data(){
      return{
        recherche:'',
        noms:[]
      }
    }, 
    computed:{
      firlterNom(){
         return this.noms.filter((nom)=> nom.includes(this.recherche))
      }
      
    }, 
    mounted(){
     return this.noms = ['Lelia', 'Jeremie', 'Gael', 'Boubacar']
    }

}
</script>