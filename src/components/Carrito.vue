<template>
   <div v-if="showModal">
    <transition name="modal">
      <div class="modal-mask">
        <div class="modal-wrapper">

        <div class="modal-dialog" role="document">
            <div class="modal-content">
                <div class="modal-header">
                    <h5 class="modal-title">Carrito</h5>
           
                    <button type="button" class="close" data-dismiss="modal" aria-label="Close">
                    <span aria-hidden="true" @click="showModal = false">&times;</span>
                    </button>
                </div>
                <div class="modal-body">
                   <tbody id="items">
                             <thead>
            <tr class="lista">
                
                <th scope="col">Producto</th><br>
                <th scope="col">Cantidad</th><br>
                <th scope="col">Acción</th><br>
                <th scope="col">Total</th>
            </tr>
            </thead>
                <Items
                    v-for="item in carrito" :key="item.id"
                    :item="item"
                />
            </tbody>
                </div>
                <div class="modal-footer">
                    <button type="button" class="btn btn-secondary" @click="showModal = false">Close</button>
                    <tr id="footer-carrito">
                <th scope="row" colspan="5" v-if="Object.keys(carrito).length === 0">Carrito vacío - comience a comprar!</th>
                <Footer v-else/>
            </tr>
                </div>
            </div>
        </div>

        </div>
      </div>
    </transition>
  </div>
  <button class="btn btn-primary " @click="showModal = true"><img class="botoncomprar" src="https://compudeep.github.io/compudeep-tienda-en-linea-/imagenes/carrito.png" alt=""></button>
</template>

<script>
import { computed } from 'vue'
import {useStore} from 'vuex'
import Items from './Items'
import Footer from './Footer'
export default {
    components: {Items, Footer},
    setup(){
        const store = useStore()
        const carrito = computed(() => store.state.carrito)

        return {carrito}
    },
    data(){
        return{
            showModal :false
        }
    }
}
</script>
<style>
.modal-mask {
  position: fixed;
  z-index: 9998;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, .5);
  display: table;
  transition: opacity .3s ease;
}

.modal-wrapper {
  display: table-cell;
  vertical-align: middle;
}
.lista{
    margin: 20px;
}
.botoncomprar{
    height: 50px;
    width: 50;
}   
</style>