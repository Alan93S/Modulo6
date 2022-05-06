<template>
  <Nav />
  <router-view />
</template>

<script>
import Nav from "@/components/Nav.vue"
import Products from "@/components/Products.vue"
export default {
components: {
Nav,
Products,

}

}
</script>

<style>

</style>


