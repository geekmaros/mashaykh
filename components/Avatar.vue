<template>
  <div class="relative">
    <img :class="imageSizeSorter" class="rounded-full" :src="src" alt="" />
  </div>
</template>

<script setup lang="ts">
import { computed } from "@vue/runtime-core";

let props = defineProps<{
  src: {
    type: String;
    required: true;
    default: "https://picsum.photos/200";
  };
  avatarLocation: {
    type: String;
    required: true;
  };
}>();

const imageSizeSorter = computed(() => {
  const { avatarLocation } = props;
  console.log(avatarLocation);
  if (avatarLocation === "navbar") {
    return "w-10 h-10 rounded-lg";
  }
  if (avatarLocation === "contact") {
    return "w-8 h-10";
  }
  if (avatarLocation === "profile") {
    return "w-24 h-24";
  }
  return "w-48 h-48";
});
</script>

<style scoped></style>
