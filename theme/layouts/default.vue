<script setup lang="ts">
import { defineComponent } from 'vue'
import ThemeLayout from './theme-layout.vue'

const components = defineComponent({ ThemeLayout })
</script>

<template>
  <theme-layout class="center">
    <div class="content default my-auto h-full flex flex-col">
    <!-- <div class="my-auto flex flex-col "> -->
      <slot />
    </div>
  </theme-layout>
</template>

<!-- <style scoped>
.content {
  p {
    font-size: 1.25rem;
  }
}
</style> -->