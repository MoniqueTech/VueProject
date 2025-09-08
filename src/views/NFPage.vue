<template>
  <section class="NotFound">
    <h1>404 – Page Not Found</h1>
    <p>Sorry, the page you’re looking for doesn’t exist.</p>
    <router-link to="/">Go back Home</router-link>
  </section>
</template>

<script>
export default { name: 'NotFound' }
</script>

<style scoped>
.NotFound {
  padding: 48px;
  text-align: center;
  background-color: #f5e0d3;
  font-family: 'Karla', sans-serif;
}
h1 {
  margin-bottom: 12px;
  color: #611e10;
  font-size: 24px;
}
p {
  margin-bottom: 20px;
}
</style>
