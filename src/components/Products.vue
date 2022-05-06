<template>
  
</template>

<script>


export default {

components: {

},
 
data(){

   return{
   
   } 
},

methods: {

     traer () {
    fetch("cosmeticos.json")
    .then(response=>response.json())
    .then((datos)=>{
    console.log(datos)
    
    
    }) 
    
    }

    
}


}

   






</script>

<style>

</style>