<template>
  <div class="container">
    <AppHeader />
    <Nuxt />
  </div>
</template>


<script>
import AppHeader from '../components/AppHeader.vue';

export default {
  components: {
    AppHeader
  }
}
</script>

<style>
*{
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body{
  font-family: Arial, Helvetica, sans-serif;
  font-size: 1rem;
  line-height: 1.6;
  background: #f4f4f4;
}

a{
  color: #666;
  text-decoration: none;
}

ul{
  list-style: none;
}

.container{
  max-width: 1200px;
  background: #fff;
  margin: 2rem auto;
  padding: 1rem 2rem;
}
</style>
