<script setup>
import { mayors } from "@/composables/useMayors";
import TaiwanMap from "./TaiwanMap.vue";
import Modal from "./Modal.vue"; // 新增 Modal 元件

// 動態圖片載入
const getImageUrl = (name) => {
  const assets = import.meta.glob("~/assets/img/*", {
    eager: true,
    import: "default",
  });
  return assets[`/assets/img/${name}`];
};

// Modal 狀態
const showModal = ref(false);
const modalContent = ref("");

// 開啟 Modal，這裡改成讀取 item.promise
const openModal = (promise) => {
  showModal.value = true;
  modalContent.value = promise;
};

// 關閉 Modal
const closeModal = () => {
  showModal.value = false;
};

// ---------視差滾動效果---------
// scrollTrigger 參數
// trigger：指定觸發的 DOM 元素
// start：何時開始觸發動畫 當元素的位置(top/bottom/center)到達視窗的位置(top/bottom/center)時
// toggleActions: "onEnter onLeave onEnterBack onLeaveBack"
// toggleActions: "play播放 none none reverse 反向播放
// scrub: true        // 動畫會隨著滾動同步（立即跟隨）
// scrub: 2           // 動畫會「平滑延遲 2 秒」跟隨滾動

// 1.呼叫 GSAP
const gsap = useGSAP(); // 呼叫一次 gsap 實體
const main = ref(); // GSAP Context 的作用域
let ctx; // 儲存 GSAP Context 回傳的物件

// 2.使用 onMounted 來初始化 GSAP Context
onMounted(() => {
  ctx = gsap.context((self) => {}, main.value);
});

// 3.組件卸載時，清除 GSAP Context
onUnmounted(() => {
  ctx.revert(); // 卸載清除動畫
});
</script>

<template lang="pug">
section#pledges(ref="main")

  img.mayors-map(src="/assets/img/mayors.svg" alt="Hero Image" class="w-full h-auto")

  .bg-green-900.text-gray-600
    div.mayors(v-for="(item, index) in mayors" :key="index")
      span.county {{ item.county }}
      p.mayor.mt-4(v-html="item.mayor")
      img.photo.block(:src="getImageUrl(item.photo)" :alt="item.title" class="w-full")
      h2.declaration {{ item.declaration }}
      .content-p.text-right.mt-2
        //- useMayors，點擊帶入 promise
        a.text-green-200.underline(href="#" @click.prevent="openModal(item.promise)", class="hover:text-green-800")
          img(src="/assets/img/icon-1.svg" alt="觀看更多", class="w-[18px] inline mr-2 -mt-1 ")
          | 觀看更多
        
        //- 引入 Modal
        Modal(:show="showModal" :content="modalContent" @close="closeModal")
 
</template>

<style scoped lang="sass">
@import '~/assets/sass/media.sass'
@import '~/assets/sass/colors.sass'
.mayors-map
  width: 100%
  height: 100vh
  object-fit: cover

.mayors
  background-color: rgba(white, 0.85)
  max-width: 420px
  width: 90%
  margin-left: auto
  margin-right: auto
  padding: 1.5rem
  position: relative
  text-align: center
  .photo
    filter: saturate(0.75)
  .county
    background-color: $green-200
    color: white
    font-size: 1.45rem
    letter-spacing: .5rem
    padding-left: 1rem
    padding-right: .5rem
    position: absolute
    left: 0
    top: 0
  .mayor
    font-size: 2.25rem
    font-weight: bold
  .declaration
    font-size: 1.45rem
    color: $gray-800
    padding-top: .5rem
    text-align: left
</style>
