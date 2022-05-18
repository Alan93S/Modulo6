<template>
   <div v-if="showModal">
    <transition name="modal">
      <div class="modal-mask">
        <div class="modal-wrapper">

        <div class="modal-dialog" role="document">
            <div class="modal-content">
                <div class="modal-header">
                    <h5 class="modal-title">Modal title</h5>
                    <tr>
                <th scope="col">#</th>
                <th scope="col">Item</th>
                <th scope="col">Cantidad</th>
                <th scope="col">Imagen</th>
                <th scope="col">Total</th>
            </tr>
                    <button type="button" class="close" data-dismiss="modal" aria-label="Close">
                    <span aria-hidden="true" @click="showModal = false">&times;</span>
                    </button>
                </div>
                <div class="modal-body">
                   <tbody id="items">
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
  <button @click="showModal = true">Click</button>
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

</style>