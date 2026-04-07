<script setup lang="ts">
import Navbar from './components/Navbar.vue';
import Footer from './components/Footer.vue';
</script>

<template>
  <div class="">
    <Navbar />
    <div class="flex-1">
      <RouterView />
    </div>
    <Footer />

  </div>
</template>

<style scoped></style>
