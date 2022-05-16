<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">

  </div>
</template>

<script>
// @ is an alias to /src

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
