<template>
  <div  v-for= "(item,index) in arregloProductos" v-bind:key="index" class="col-md-6">
   <div class="card">
    <div class="inner-card"> \
      <img
          class="imagen  img-fluid rounded "
          v-bind:src="item.imagen"
          v-bind:alt="item.name"
        />
      <div class="d-flex justify-content-between align-items-center mt-3 px-2">
         <h4>{{item.nombre}} </h4> <span class="heart"><i class="fa fa-heart"></i></span>
         </div>
         <div class="mt-2 px-2"> <small>Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium</small> </div>
         <div class="px-2">
         <h3>${{item.precio}}</h3>
        </div>
        <div class="px-2 mt-3"> <button class="btn btn-primary px-3">Buy Now</button> <button class="btn btn-outline-primary px-3">Add to cart</button> </div>
    </div>
</div>
    </div>
  
</template>

<script>



   export default {   
  name: 'Products',

  data: () =>({
    arregloProductos:[]
  }),

  mounted () {
    fetch("cosmeticos.json")
    .then(response=>response.json())
    .then((datos)=>{this.arregloProductos=datos;})
    },
}
</script>
<style>
.imagen{
    width: 200px;
    height: 200px;
}
</style>
