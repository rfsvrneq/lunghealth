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

// 呼叫一次 gsap 實體
const gsap = useGSAP();

// 建立地圖 refs 陣列
const mapRefs = ref([]);

// 動態綁定多個地圖 ref 元素
const setMap = (index) => (el) => {
  if (el) mapRefs.value[index] = el;
};

// scrollTrigger 參數
// trigger：指定觸發的 DOM 元素
// start：何時開始觸發動畫 當元素的位置(top/bottom/center)到達視窗的位置(top/bottom/center)時
// toggleActions: "onEnter onLeave onEnterBack onLeaveBack"
// toggleActions: "play播放 none none reverse 反向播放
// scrub: true        // 動畫會隨著滾動同步（立即跟隨）
// scrub: 2           // 動畫會「平滑延遲 2 秒」跟隨滾動

onMounted(() => {
  mapRefs.value.forEach((el, index) => {
    gsap.fromTo(
      el,
      {
        marginTop: "-150vh",
        opacity: 0,
      },
      {
        marginTop: "-150vh",
        opacity: 1,
        scrollTrigger: {
          trigger: el,
          start: "top 80%",
          end: "top 20%",
          // scrub: "2",
          toggleActions: "play none none reverse",
        },
      }
    );
  });
});
</script>

<template lang="pug">

h2.text-5xl 開始滾動開始滾動開始滾動開始滾動開始滾動
h2.text-5xl 開始滾動開始滾動開始滾動開始滾動開始滾動
h2.text-5xl 開始滾動開始滾動開始滾動開始滾動開始滾動

//- 地圖滾動區塊
.parallax_map_container(v-for="(item, index) in mayors" :key="index" :ref="setMap(index)")
  .parallax_map_bg
    img(:src="getImageUrl(item.map)")

  .parallax_map
    .promise
      span.text-2xl.text-green-300 {{ item.county }}
      h2.text-3xl.text-green-700.mb-5 {{ item.declaration }}
      img.mx-auto(:src="getImageUrl(item.photo)" :alt="item.title" class="w-8/12 lg:w-10/12")

h2.text-5xl 結束滾動結束滾動結束滾動結束滾動結束滾動
h2.text-5xl 結束滾動結束滾動結束滾動結束滾動結束滾動
h2.text-5xl 結束滾動結束滾動結束滾動結束滾動結束滾動
    
</template>

<style scoped lang="sass">

.parallax_map_container
  width: 100%
  height: 400vh
  position: relative


.parallax_map
  width: 100%
  height: 100%
  position: absolute
  pointer-events: none
  z-index: 1

.promise
  width: 460px
  height: min-content
  padding: 2rem
  background-color: rgba(white, .85)
  margin-top: 5%
  margin-right: 5%
  margin-left: auto


.parallax_map_bg
  width: 100%
  height: 100vh
  position: sticky
  top: 0
  img
    width: 100%
    height: 100%
    object-fit: cover
</style>
