<template>
  <div class="w-120 min-h-50">
    <div class="text-4xl mb-5 color-black font-size-10">
      Anim?
      <div class="shaow-lg flex flex-col rounded-md bg-slate-50">
        <!--背景图-->
        <div class="flex-1/10">
          <Transition
            mode="out-in"
            enter-active-class="transition-all duration-1000 ease-in-out opacity-100"
            leave-active-class="transition-all duration-1000 ease-in-out opacity-0"
          >
            <img
              :key="count"
              :src="currentBackground"
              class="rounded-t-md"
              alt="background"
            />
          </Transition>
        </div>
        <!--描述与选择-->
        <div class="flex-2/5 flex gap5 p-1">
          <!--头像区-->
          <img
            v-for="anim in animList"
            :key="anim.key"
            @click="handleSwitch(anim.key)"
            class="h-12 p-2 rounded shadow-md cursor-pointer hover:scale-110 transition-all"
            :src="`../../../public/img/anim/${anim.key}/icon.jpg`"
            alt="Avater"
          />
        </div>
        <!--介绍区-->
        <div class="flex-1/5 px-5 pb-5 flex flex-col">
          <h1 class="font-bold font-size-8">{{ currentAnim?.name }}</h1>
          <p class="text-gray-500 font-size-6">
            {{ currentAnim?.description }}
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { computed, ref } from "vue";
import { Transition } from "vue";
const animList = [
  {
    key: "Denpa Onna to Seishun Otoko",
    name: "Denpa Onna to Seishun Otoko",
    description: "Commemorating my dear monment",
  },
  {
    key: "Grand Blue",
    name: "Grand Blue",
    description: "Just diving...",
  },
  {
    key: "Code Geass",
    name: "Code Geass",
    description: "My childhood",
  },
];
const currentAnimKey = ref("Denpa Onna to Seishun Otoko");
const currentAnim = computed(() => {
  return animList.find((anim) => anim.key === currentAnimKey.value);
});
const currentBackground = computed(
  () => `/img/anim/${currentAnimKey.value}/background.jpg`
);
const count = ref(0);
function handleSwitch(key: string) {
  if (currentAnimKey.value !== key) {
    currentAnimKey.value = key;
    count.value++;
  }
}
</script>

<style scoped></style>
