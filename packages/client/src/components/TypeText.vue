<template>
  <div class="flex" >
    <div ref="containerRef"></div>
  </div>
</template>

<script setup lang="ts">
import Typed from "typed.js";
import { onMounted, onUnmounted, ref } from "vue";
const {
  text,
  typeSpeed = 50,
  startDelay = 1000,
} = defineProps<{
  text: string;
  typeSpeed?: number;
  startDelay?: number;
}>();
let typed: Typed | null = null;
const containerRef = ref<HTMLElement | null>(null);
onMounted(() => {
  if (containerRef.value) {
    typed = new Typed(containerRef.value, {
      strings: [text],
      startDelay: startDelay,
      typeSpeed: typeSpeed,
    });
  }
});
onUnmounted(() => {
  typed?.destroy();
});
</script>

<style scoped>
.bg{
  display: flex;
  align-items: center;
  font-size:46px;
  font-weight:bolder;
  height:220px;
  line-height: 220px;
  background-color: rgb(31, 205, 240);
  color:white;
}
</style>
