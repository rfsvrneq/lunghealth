<script setup>
import TaiwanMap from "./TaiwanMap.vue";
import { mayors } from "@/composables/useMayors";

// 動態圖片載入
const getImageUrl = (name) => {
  const assets = import.meta.glob("~/assets/img/*", {
    eager: true,
    import: "default",
  });
  return assets[`/assets/img/${name}`];
};

const gsap = useGSAP(); // 呼叫一次 gsap 實體

const main = ref(); // GSAP Context 的作用域
let ctx; // 儲存 GSAP Context 回傳的物件

// scrollTrigger 參數
// trigger：指定觸發的 DOM 元素
// start：何時開始觸發動畫 當元素的位置(top/bottom/center)到達視窗的位置(top/bottom/center)時
// toggleActions: "onEnter onLeave onEnterBack onLeaveBack"
// toggleActions: "play播放 none none reverse 反向播放
// scrub: true        // 動畫會隨著滾動同步（立即跟隨）
// scrub: 2           // 動畫會「平滑延遲 2 秒」跟隨滾動

onMounted(() => {
  ctx = gsap.context((self) => {
    const boxes = self.selector(".box");
    boxes.forEach((box) => {
      gsap.from(box, {
        x: -300,
        scrollTrigger: {
          trigger: box,
          start: "top center",
          end: "bottom bottom",
          scrub: 2,
        },
      });
    });
  }, main.value);
});

onUnmounted(() => {
  ctx.revert(); // 卸載清除動畫
});
</script>

<template lang="pug">
section(ref="main")
 .box.bg-red-300 Basic ScrollTrigger in Nuxt 3
 .box.bg-green-300 Scroll down to see the magic happen!!
 .box.bg-blue-300 The End!
</template>

<style scoped lang="sass">
@import '~/assets/sass/media.sass'

.box
  font-size: 3rem
  height: 100vh
  display: flex
  align-items: center
  justify-content: center
  +m-768
   font-size: 2.5rem
</style>
