<template>
  <div v-if="type !== 'No Syrup'" class="syrup" :style="{ backgroundColor: syrupColor }"></div>
</template>

<script setup lang="ts">
import { computed } from 'vue'

// receives the syrup type from Beverage.vue
const props = defineProps<{ type: string }>()

// gives color for each syrup
const syrupColor = computed(() => {
  if (props.type === 'Vanilla') return '#f3e5ab'
  if (props.type === 'Caramel') return '#c68e17'
  if (props.type === 'Hazelnut') return '#4c2e12ff'
})
</script>

<style scoped>
.syrup {
  transform: translateY(400%);
  background-color: #c6c6c6;
  position: relative;
  width: 100%;
  height: 20%;
  animation: pour-tea 2s 1s forwards;
  z-index: 2;
  border-radius: 4px;
}
</style>
