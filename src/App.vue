<script setup>
import { RouterView } from 'vue-router'
import Navigation from './views/utils/NavigationBar.vue'
import Footer from './views/utils/FooterBar.vue'
</script>

<template>
  <navigation />
  <main>
    <RouterView />
  </main>
  <Footer />
</template>

<style></style>
