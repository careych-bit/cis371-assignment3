<template>
<div
  class="baseBeverage"
  :style="{ backgroundColor: baseColors[base] }"
></div>

</template>


<script setup lang="ts">
type Props = {
  base: string;
};

defineProps<Props>();

const baseColors: Record<string, string> = {
  Coffee: '#6f4e37',
  'Green Tea': '#a4bb72',
  'Black Tea': '#8b4513',
};
</script>


<style scoped>
.baseBeverage {
  position: relative;
  width: 100%;
  height: 100%;
  bottom: 0;
  animation: pour-tea 2s;
  z-index: 300;
  /* // border-radius: 0.05em 0.05em 2.2em 2.2em; */
}
</style>
