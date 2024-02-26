<script setup lang="ts">
import { computed, defineComponent } from 'vue'

import ThemeLayout from './theme-layout.vue'

const components = defineComponent({ ThemeLayout })
const props = defineProps<{
  image?: string
  leftClass?: string
  rightClass?: string
  equal?: Boolean
}>();
</script>

<template>
  <theme-layout layout-class="image image-left image-left-pop" content-class="relative h-full grid grid-cols-12">
    <div v-if="image"
      :class="[
        equal ? 'col-span-6' : 'col-span-4',
        'my-auto h-full flex justify-center items-center',
        leftClass
      ]"
      :style="{
        backgroundImage: `url(${image})`,
        backgroundSize: 'cover',
        backgroundPosition: 'left',
      }"
    >
      <div class="h-full w-full" style="backdropFilter: blur(6px)">&nbsp;</div>
        <div class="absolute left-15">
          <div :style="{
            boxShadow: '0px 10px 30px rgba(0,0,0,0.7)',
            zIndex: '5',
          }">
            <img :src="image" class="w-[450px]" alt="" />
          </div>
        </div>
    </div>
    <div :class="[
      'slidev-layout my-auto',
      image ? 'col-span-6' : 'col-span-12',
      equal ? 'col-span-6' : 'col-span-8',
      rightClass
    ]">
      <slot />
    </div>
  </theme-layout>
</template>

<style>
.slidev-layout.image .slidev-content {
  padding: 0;
  background: var(--slidev-theme-image-background);
}
</style>
