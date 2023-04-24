<template>
  <header>
    <div class="logo">
      <h3>BMO</h3>
    </div><!-- /.logo -->
    <div class="menu">
      <router-link to="/">Home</router-link> |
      <router-link to="/contact">Contato</router-link>
    </div><!-- /.menu -->
  </header>
</template>

<script>
export default {
  name: 'HeaderComponent'
}
</script>

<style scoped>
header{
  display:flex;
  justify-content: space-evenly;
  align-items: center;
  background-color: #ccc;
  height: 40px;
}

.logo h3{
  color: #1034c2;
}
a {
  font-weight: bold;
  color: #2c3e50;
}

a.router-link-exact-active {
  color: #1034c2;
}
</style>
