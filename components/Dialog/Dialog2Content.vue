<script setup></script>

<template lang="pug">
div.text-gray-500
  .dialog-ttl
    p Ｂ.藥物副作用：
    p 藥物有哪些副作用？是否影響日常生活？我可以透過其他方式來改善副作用嗎？

  .dialog-p
    p 在治療策略的規劃上，副作用也是一個重要的課題。應該了解各個藥物有哪些副作用？這些副作用有沒有辦法妥善管理？長期下來是否可以用的久、且維持一定的生活品質？
    
    p
      span.text-xl.font-genjyuu-bold.text-gray-500.block 例如：
      span.text-orange-500.font-genjyuu-bold 化學治療
      | 會出現的副作用因人而異，包括如
      span.text-orange-500 噁心、嘔吐、腹瀉、疲倦感及口腔潰爛、掉髮等；
      | 至於
      span.text-orange-500.font-genjyuu-bold 放射線治療
      | 的副作用可能依照
      span.text-orange-500 不同照射位置而各異
      | ；
      span.text-orange-500.font-genjyuu-bold 標靶藥物
      | 的副作用通常會比化療及放療低，常見副作用如
      span.text-orange-500 噁心、腹瀉、皮膚症狀或甲溝炎等
      | 。
    p 建議與主治醫師討論副作用的預防及照護方式，同時維持均衡飲食、多做休息、並適度運動，以渡過這些暫時性的副作用。

    small (詳見本一站式指南-生活照護盤點：出現副作用怎麼辦？)

</template>

<style scoped lang="sass">
.dialog-ttl
  @apply text-xl font-genjyuu-bold leading-8 text-justify

.dialog-p
  @apply mt-5 font-genjyuu-light text-gray-600 text-justify
  p
    @apply mb-3 
</style>
