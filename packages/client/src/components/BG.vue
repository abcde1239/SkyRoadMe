<template>
  <div class="bg">
    <TypeText
      :text="text"
      class="m-auto color-white font-bold text-shadow-sm text-6xl"
    />
  </div>
</template>

<script setup lang="ts">
import TypeText from "./TypeText.vue";
const { text } = defineProps<{
  text: string;
}>();
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
