<template>
  <div class="w-120 min-h-50">
    <div class="text-4xl mb-5 color-black font-size-10">Game?</div>
    <div class="shadow-lg flex flex-col rounded-md bg-slate-50">
      <!-- 游戏背景图 -->
      <div class="flex-1/10">
        <Transition
          mode="out-in"
          enter-active-class="transition-all duration-1000 ease-in-out opacity-100"
          leave-active-class="transition-all duration-1000 ease-in-out opacity-0"
        >
          <img
            :key="count"
            :src="currentGameBackground"
            class="rounded-t-md"
            alt="Background"
          />
        </Transition>
      </div>
      <!-- 游戏描述与选择 -->
      <div class="flex-2/5 flex gap-5 p-1">
        <div
          v-for="game in gameList"
          :key="game.key"
          @click="handleSwitch(game.key)"
        >
          <!-- 头像区 -->
          <img
            class="h-12 rounded-full shadow-md cursor-pointer hover:scale-110 transition-all"
            :src="`/img/game/${game.key}/icon.jpg`"
            alt="Avatar"
          />
        </div>
      </div>

      <!-- 介绍区 -->
      <div class="flex-1/5 px-5 pb-5 flex flex-col">
        <h1 class="font-bold font-size-8">{{ currentGame?.name }}</h1>
        <p class="text-gray-500 font-size-6">
          {{ currentGame?.description }}
        </p>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { computed, ref } from "vue";

const gameList = [
  {
    key: "Terraria",
    name: "Terraria",
    description: "My favorite game!",
  },
  {
    key: "Calamity",
    name: "Calamity!",
    description: "My favorite mod",
  },
];
const currentGameKey = ref("Terraria");
const currentGame = computed(() => {
  return gameList.find((game) => game.key === currentGameKey.value);
});
const currentGameBackground = computed(
  () => `/img/game/${currentGameKey.value}/background.jpg`
);
const count = ref(0);
function handleSwitch(key: string) {
  if (currentGameKey.value !== key) {
    currentGameKey.value = key;
    count.value++;
  }
}
</script>
