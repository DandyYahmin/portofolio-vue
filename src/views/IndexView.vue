<script setup lang="ts">
  import Navbar from '@/components/NavbarSection.vue'
  import LoadingScreen from '@/components/LoadingScreen.vue';
</script>

<template>
  <main>
    <LoadingScreen 
      :time=2000
      backgroundColor="#1C1917"
      loaderColor="#FACC15"
    />
    <Navbar />
  </main>
</template>
