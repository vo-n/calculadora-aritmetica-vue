<script setup>
  import Header from './components/Header.vue';
  import Calculator from './components/Calculator.vue';
  import Footer from './components/Footer.vue'; 
</script>

<template>
  <div class="container">
    <Header />
    <Calculator />
    <Footer />
  </div>
</template>

<style scoped>
  .container {
    color: aliceblue;
    background-color: #6883BA;
  }
</style>
