<template>
  <div
    :class="darkMode ? 'dark' : ''"
    class="h-screen w-full bg-white dark:bg-primary transition-all duration-300 ease-in-out"
  >
    <Navbar />
    <slot />
  </div>
</template>

<script setup lang="ts">
import { ref } from "@vue/runtime-core";

const darkMode = ref(true);
</script>

<style scoped></style>
