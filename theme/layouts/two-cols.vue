<script setup lang="ts">
import { defineComponent } from 'vue'

import ThemeLayout from './theme-layout.vue'

const components = defineComponent({ ThemeLayout })
const props = defineProps({
  leftClass: {
    type: String,
    default: 'col-span-6'
  },
  rightClass: {
    type: String,
    default: 'col-span-6'
  }
});

</script>

<template>
  <theme-layout class="two-columns">
    <div class="content my-auto h-full relative grid grid-cols-12">
      <div class="leftColumn" :class="leftClass">
        <slot />
      </div>

      <div class="rightColumn" :class="rightClass">
        <slot name="right" />
      </div>
    </div>
  </theme-layout>
</template>
