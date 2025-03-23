<template>
   <div> 
  <input type="text" v-model="message" placeholder="Tape quelque chose">
  <p> Texte inverse : {{ reverseMessage }}</p>
</div>
</template>

<script>
export default{
   data(){
    return{
      message : ''
    }
   }, 
   computed:{
    reverseMessage(){
      return this.message.split('').reverse().join('')
    }
   }
}
</script>


<style scoped> 
</style>