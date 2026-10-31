
<template>
  <div
    class="syrup"
    :style="{ backgroundColor: syrupColors[syrup] }"
  ></div>
</template>



<script setup lang="ts">
type Props = {
  syrup: string;
};

defineProps<Props>();

const syrupColors: Record<string, string> = {
  Vanilla: '#d9af74',
  Caramel: '#a86734',
  Hazelnut: '#8b5936',
};
</script>

<style lang="scss" scoped>
.syrup {
  transform: translateY(400%);
  background-color: #c6c6c6;
  position: relative;
  width: 100%;
  height: 20%;
  animation: pour-tea 2s 1s forwards;
  z-index: 2;
}
</style>
