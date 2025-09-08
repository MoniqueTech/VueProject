<template>
<div class="home">
<h1>Monique Lotriet</h1>
<p class="SubHeader">My Front-End Journey</p>
<p class="SubText"> Hi, I'm learning how to build websites from scratch.<br> This page is my first project, and it’s where I’ll share my progress as I grow.</p>
</div>
</template>
<script>
export default {
    name: 'HomePage'
}
</script>
<style scoped>
.home  {
  margin: 0;
  border: 0;
  padding: 0;
  background-color: #f5e0d3;
  font-family: 'Karla', sans-serif;
  font-size: 13px;
 
}

h1 {
  padding-bottom: 10px;
  text-align: center;
  background-color: #611e10;
  color: #f5e0d3;
  font-size: 20px; 
  text-transform: uppercase;
  font-weight: 300;
  font-family: 'Playfair Display', serif;
}

.SubHeader {
  font-size: 14px; 
  color: #f5e0d3;
  padding-bottom: 10px;
  font-style: italic;
  text-align: center;
  background-color: #611e10;
  line-height: 18px;

}

.SubText {
  font-size: 10px;  
  color: #f5e0d3;
  padding-bottom: 10px;
  padding-top: 10px;
  font-style: italic;
  text-align: center;
  background-color: #611e10;
  line-height: 18px;
}

</style>