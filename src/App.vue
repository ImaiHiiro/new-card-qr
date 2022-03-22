<script setup lang="ts">
import { RouterView } from "vue-router";
</script>

<template>
  <nav class="navbar navbar-light bg-light">
    <div class="container-fluid">
      <span class="navbar-brand mb-0 h1">Okunoto Coupons</span>
    </div>
  </nav>
  <div class="app-content-area">
    <RouterView />
  </div>
</template>

<style scoped>
@import "@/assets/base.css";
.app-content-area {
  padding-top: 16px;
}
</style>
