<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">

      <h1>INICIO</h1>
  </div>
</template>

<script>
// @ is an alias to /src
import auth from "@/logic/auth";
export default {
  name: 'HomeView',
  components: {
  },

   computed: {
    userLogged(){
    return auth.getUserLogged();
    }
  }
}
</script>
