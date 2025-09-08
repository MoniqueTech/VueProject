<template>
  <nav class="navigation">
    <router-link to="/" class="nav-link">Home</router-link>
    <router-link to="/about" class="nav-link">About</router-link>
    <router-link to="/contact" class="nav-link">Contact</router-link>
  </nav>
</template>

<script>
export default { name: 'NavBar' }
</script>

<style scoped>
.navigation { padding: 1rem; background: #f8f9fa; }
.nav-link { margin-right: 1rem; text-decoration: none; color: #495057; }
.router-link-active { font-weight: bold; color: #ff40009f; }
</style>
