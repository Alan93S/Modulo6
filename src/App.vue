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
  <Nav/>
  <router-view />
  
</template>

<script>
import Nav from './components/Nav.vue'



export default {
  name: 'App',
  components: {
   Nav
  },
 
}
</script>