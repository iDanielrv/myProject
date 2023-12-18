<script setup>
import { RouterLink, RouterView } from 'vue-router'
import AppBar from '../src/components/AppBar.vue'
</script>

<template>
  <div class="container">
    <AppBar></AppBar>
    <div class="space"></div>
    <div class="pageContent">
      <RouterView />
    </div>

  </div>
</template>

<style>
.space {
  height: 64px;
}

.pageContent {
  background-color: #2B2B2B;
}

</style>
