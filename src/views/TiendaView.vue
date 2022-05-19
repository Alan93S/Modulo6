<!-- <template>
<Nav />
<router-view />
  <div class="container">
    
    <h1>Carrito con vue.js</h1>
    <hr>
    <Carrito />
    <div class="row">
      <div 
        v-for="producto of productos" :key="producto.id"
        class="col-12 col-sm-4 col-md-3 col-lg-2 mb-3 mb-3"
      >
        <Products 
          :producto="producto"
        />
      </div>
    </div>
  </div>
</template>

<script>
import {useStore} from 'vuex'
import { computed, onMounted } from 'vue'

import Carrito from './components/Carrito'
import Nav from './components/Nav.vue'
import Products from './components/Products.vue'

export default {
  name: 'App',
  components: {
    
    Carrito,
    Nav,
    Products
},
  setup(){
    const store = useStore()
    onMounted(async() => {
      store.dispatch('fetchData')
    })

    const productos = computed(() => store.state.productos)

    return {productos}
  }
}
</script> -->


<template>

  <div class="container">
    <h1>Carrito con vue.js</h1>

    <hr>
    <Carrito />
    <div class="row">
      <div> 
<input type="text" v-model="buscar" class="form-control" placeholder="Ejemplo: Charmander"/>
 
</div>
      <div 
        v-for="producto of productos" :key="producto.id"
        class="col-12 col-sm-4 col-md-3 col-lg-2 mb-3 mb-3"
      >
        <Card 
          :producto="producto"
        />
      </div>
    </div>
  </div>
</template>

<script>

import {useStore} from 'vuex'
import { computed, onMounted } from 'vue'
import Card from '@/components/Card'
import Carrito from '@/components/Carrito'
import Search from "@/components/Search.vue";
import datos from "C:/Users/lukas/OneDrive/Escritorio/Modulo6/public/cosmeticos.json"

export default {
  name: 'App',
  components: {
    Card, Carrito, Search
  },
 
  data() {
    return {
      buscar: ''
    }
  },
  setup(){
    const store = useStore()
    onMounted(async() => {
      store.dispatch('fetchData')
    })
    
    // const productos = computed(() => store.state.productos)

    // return {productos}
  },

computed: {
    productos() {
      return datos.filter(producto => {
        return producto.nombre.toLowerCase().includes(this.buscar.toLowerCase());
      });
    },
 
  }
  
}
</script>

