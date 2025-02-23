<template>
  <div class="bg">
    <div ref="containerRef" class="m-auto color-white font-bold text-shadow-sm text-6xl"></div>
  </div>
</template>

<script setup lang="ts">
import Typed from "typed.js";
import { onMounted, onUnmounted, ref } from "vue";
let typed: Typed | null = null;
const containerRef = ref<HTMLElement | null>(null);
onMounted(() => {
  if (containerRef.value) {
    typed = new Typed(containerRef.value, {
      strings: ["这简直就是我呀", "呃呃谁家丹羽真", "哈哈我星中小海呢?"],
      startDelay: 1000,
      typeSpeed: 100,
      shuffle: true,
    });
  }
});
onUnmounted(() => {
  typed?.destroy();
});
</script>

<style scoped>
.bg {
  display: flex;
  align-items: center;
  font-size: 46px;
  font-weight: bolder;
  height: 150px;
  line-height: 220px;
  background-color: rgb(31, 205, 240);
  color: white;
}
</style>
