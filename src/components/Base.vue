<template>
  <div class="baseBeverage" :style="{ backgroundColor: baseColor }"></div>
</template>

<script setup lang="ts">
import { computed } from 'vue'

// receives which base drink was chosen
const props = defineProps<{ type: string }>()

// gives a simple color for each base drink
const baseColor = computed(() => {
  if (props.type === 'Coffee') return '#936c45ff'
  if (props.type === 'Green Tea') return '#8fbc8f'
  if (props.type === 'Black Tea') return '#452818ff'
})
</script>

<style scoped>
.baseBeverage {
  position: relative;
  width: 100%;
  height: 100%;
  bottom: 0;
  animation: pour-tea 2s;
  z-index: 300;
  border-radius: 0.05em 0.05em 2.2em 2.2em;
}
</style>
