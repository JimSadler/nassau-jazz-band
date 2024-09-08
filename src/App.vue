<script setup>
import {  RouterView } from 'vue-router'
import Navigation from './views/utils/NavigationBar.vue'

</script>

<template>
  <navigation />
  <main >
    <RouterView />
  </main>
</template>

<style>

</style>
