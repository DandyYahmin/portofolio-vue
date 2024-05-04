<script setup lang="ts">
  import Navbar from '@/components/NavbarSection.vue'
  import LoadingScreen from '@/components/LoadingScreen.vue';
</script>

<template>
  <main>
    <LoadingScreen 
      :time=4699
      backgroundColor="#1C1917"
      loaderColor="#44403C"
      :motivationText=true
      :loader=true
    />
    <Navbar />
  </main>
</template>
