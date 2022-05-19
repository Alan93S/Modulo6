<!-- <template>
<input type="text" v-model="buscar" class="form-control" placeholder="Busca tu producto "/>
<div v-for= "(item,index) in items" :key="index" class="col-md-3">
<div class="card shadow">
<h5 class="card-title">{{item.nombre}}</h5>
<img class="card-img-top card-image" :src="item.imagen" alt="Card image cap">
<div class="card-body">
<h5 class="card-title">${{item.precio}}</h5>
<p class="card-text desc">{{}}</p>
<p class="card-text ">{{}}</p>
<p class="card-text"><small class="text-muted">Rating:{{}}/5</small></p>
<div class="d-flex" style="justify-content: space-around;">
<button class="btn btn-warning btn-text" type="button">Agregar al Carrito!</button>
<button class="btn btn-primary" type="button">Comprar Ahora!</button>
</div>
</div>
</div>
</div> 
</template>

<script>


export default { 
name: 'Products',

data: () =>({
arregloProductos:[],
buscar: ""
  

}),
mounted () {
fetch("cosmeticos.json")
.then(response=>response.json())
.then((datos)=>{this.arregloProductos=datos;})
},
computed: {
    items() {
      return this.arregloProductos.filter(item => {
        return item.nombre.toLowerCase().includes(this.buscar.toLowerCase());
      });
 
  },
}
}

</script>
<style scoped>
.card-image{
height: 200px; 
padding: 25px;
 width: 200px;
}
.card-img-top{
width: 190px;
margin: 0 auto;
}
.card-text{
font-size: 13px;
}
.card-title{
font-size: 18px;
font-weight: 600;
margin: 20px auto 5px auto;

}
.card-title:hover{
text-decoration: underline;
cursor: pointer;
}
button{
display: flex !important;
justify-content: center;
justify-content:space-evenly;
}
.card:hover{
transform: translate(0, -5px);
border:1px solid black
}
.card-body{
margin-top: 0px;
}
</style> -->



<template>
    <div class="card h-100 w-100 ">
        <img :src="producto.imagen" :alt="`imagen ${producto.nombre}`" class="card-img-top h-50 w-50 " />
        <div class="card-body">
        <h5 class="card-title">{{producto.nombre}}</h5>
        <p class="card-text">$ <span>{{producto.precio}}</span></p>
        <button class="btn btn-dark" @click="comprar(producto)">Comprar</button>
        </div>
    </div>
</template>

<script>
import datos from "C:/Users/lukas/OneDrive/Escritorio/Modulo6/public/cosmeticos.json"
import {useStore} from 'vuex'
export default {
    props: ['producto'],
     data() {
    return {
      buscar: ''
    }
  },
    setup(){
        const store = useStore()
        const comprar = producto => {
            store.dispatch('agregarCarrito', producto)
        }
        return {comprar}
    },
     computed: {
    items() {
      return datos.filter(producto => {
        return producto.nombre.toLowerCase().includes(this.buscar.toLowerCase());
      });
    },
 
  }
}


</script>