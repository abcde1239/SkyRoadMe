<template>
  <div class="w-120 min-h-50">
    <div class="text-4xl mb-5 color-black font-size-10">
      Me?
      <div class="shaow-lg flex flex-col rounded-md bg-slate-50">
        <div class="flex-1/10">
          <img
            class="round-t-md max-height- max-width"
            src="../../../public/img/Azusa2.jpg"
          />
        </div>

        <div class="flex-2/5 flex gap5 p-1">
          <!-- 头像区 -->
          <img
            class="h-12 rounded-full"
            src="../../../public/img//abcde.jpg"
            alt="Avatar"
          />
          <!-- 介绍区-->
          <div class="flex flex-col">
            <h1 class="font-bold text-gray font-size-6">Sky Road</h1>
            <p class="text-gray-500 font-size-6">A Web Developer.</p>
          </div>
          <!--链接区-->
          <div class="flex ml-auto gap-1">
            <Icon
              icon="uil:github"
              class="cursor-pointer"
              size="14"
              @click="() => jumpTo('https://github.com/abcde1239')"
            />
            <Icon
              icon="material-symbols:book-2"
              class="cursor-pointer"
              size="14"
              @click="() => jumpTo('')"
            />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { Icon } from "@iconify/vue";
function jumpTo(url: string) {
  window.location.href = url;
}
</script>

<style scoped></style>
