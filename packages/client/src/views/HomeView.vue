<script setup lang="ts">
import Epilogue from "@/components/Epilogue.vue";
import Prologue from "@/components/Prologue.vue";
import { onMounted, reactive, ref } from "vue";
import AOS from "aos";
import "aos/dist/aos.css";
const totalHeight = ref("100%");
const unitStyle = reactive({ height: "100%" });
onMounted(() => {
  AOS.init({
    mirror: true,
  });
  totalHeight.value = `${window.innerHeight * 5}px`;
  unitStyle.height = `${window.innerHeight}px`;
});
import BG from "@/components/BG.vue";
import Footer from "@/components/Footer.vue";
import PostCard from "@/components/Profile/PostCard.vue";
</script>

<template>
  <div id="app" class="flex flex-col" :style="{ height: totalHeight }">
    <div class="image_1" style="flex">
      <Prologue :style="unitStyle" />
    </div>
    <BG text="好表妹藤和艾莉欧" />
    <div class="image_2" style="flex">
      <div class="p-5">
        <PostCard data-aos="flip-right" class="ml-50" />
      </div>
    </div>
    <BG text="好集美前川" />
    <div class="image_3" style="flex"></div>
    <BG text="好闺蜜御船流子" />
    <div class="image_4" style="flex"></div>
    <BG text="好姑姑藤和女女" />
    <div class="image_5" style="flex">
      <Epilogue :style="unitStyle" class="mt-auto" />
    </div>
    <Footer />
  </div>
</template>
<style scoped>
.image_1 {
  background-image: url(../../public/img/background01.jpg);
  background-position: 0 0;
  background-attachment: fixed;
  background-size: cover;
  height: 932px;
  width: 100%;
  z-index: -1;
}
.image_2 {
  background-image: url(../../public/img/background02.jpg);
  background-position: 0 0;
  background-attachment: fixed;
  background-size: cover;
  height: 932px;
  width: 100%;
  z-index: -1;
}
.image_3 {
  background-image: url(../../public/img/background03.jpg);
  background-position: 0 0;
  background-attachment: fixed;
  background-size: cover;
  height: 932px;
  width: 100%;
  z-index: -1;
}
.image_4 {
  background-image: url(../../public/img/background04.jpg);
  background-position: 0 0;
  background-attachment: fixed;
  background-size: cover;
  height: 932px;
  width: 100%;
  z-index: -1;
}
.image_5 {
  background-image: url(../../public/img/background05.jpg);
  background-position: 0 0;
  background-attachment: fixed;
  background-size: cover;
  height: 932px;
  width: 100%;
  z-index: -1;
}

#app {
  position: relative;
  background-color: rgba(31, 33, 41, 0.4);
  z-index: 0;
  z-index: -1;
}
</style>
