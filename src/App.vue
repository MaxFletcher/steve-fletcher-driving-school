<script setup lang="ts">
import { RouterView } from 'vue-router'
import MainHeader from './components/MainHeader.vue'
</script>

<template>
  <MainHeader />

  <div class="page-content">
    <RouterView />
  </div>
</template>

<style scoped>
.page-content {
  padding: 2rem;
}
</style>
