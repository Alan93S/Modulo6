<template>
  <nav class="navbar navbar-expand-lg navbar-light bg-light">
    <div class="container-fluid">
      <img src="" alt="" height="100px" width="100px" />
      <a class="navbar-brand" href="#">Cosmetica Natural</a>
      <button
        class="navbar-toggler"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#navbarSupportedContent"
        aria-controls="navbarSupportedContent"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav me-auto mb-2 mb-lg-0">
          <li class="nav-item">
            <a class="nav-link active" aria-current="page" href=""
              ><router-link to="/">Inicio</router-link></a
            >
          </li>
          <li class="nav-item">
            <a class="nav-link" href=""
              ><router-link to="/tienda">Tienda</router-link></a
            >
          </li>

          <li class="nav-item">
            <a class="nav-link" href=""
              ><router-link to="/contacto">Contacto</router-link></a
            >
          </li>

          <li class="nav-item">
            <a class="nav-link" href=""
              ><router-link to="/login">Login</router-link></a
            >
          </li>
        </ul>
        <Search />
      </div>
    </div>
  </nav>
</template>

<script>
import Search from "@/components/Search.vue";

export default {
  name: "Nav",
  components: {
    Search,
  },
};
</script>

<style>
</style>