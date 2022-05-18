<template>
  <tr>
    
    <td>{{item.nombre}}</td>
    <br>
    <td>{{item.cantidad}}</td><br>
    <img class="imagencarro" :src="item.imagen" alt="">
    <td>
        <button class="btn btn-info btn-sm" @click="aumentar(item.id)">
            +
        </button>
        <button class="btn btn-danger btn-sm" @click="disminuir(item.id)">
            -
        </button>
    </td>
    <td>${{item.precio * item.cantidad}}</td>
  </tr>
</template>

<script>
import {useStore} from 'vuex'
export default {
    props: ['item'],
    setup(){
        const store = useStore()
        const aumentar = id => {store.commit('aumentar', id)}
        const disminuir = id => {store.commit('disminuir', id)}
        return {aumentar, disminuir}
    }
}
</script>

<style>
.imagencarro{
    height: 100px;
    width: 100px;
}
</style>