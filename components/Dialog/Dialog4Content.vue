<script setup></script>

<template lang="pug">
div.text-gray-500
  .dialog-ttl
    p Ｄ.經濟考量：
    p 治療的藥物有健保給付嗎？我的經濟狀況可以負擔抗藥後的治療嗎？

  .dialog-p
    p 對抗癌症就像跑馬拉松，除了前述的療效、生活品質、抗藥後的治療規劃等面向外，經濟考量也是一個重要的評估重點。在台灣，在政府的努力下大多病患都有機會可以受到健保藥物的治療。因此，除了謹慎選擇第一線藥物，抗藥後後一線的藥物是否也有健保的支持，也應是初確診病患可以提前檢視評估的。
    
    p 
      span.font-genjyuu-bold.text-gray-500 以國人常見的晚期肺癌 EGFR 基因突變病人為例，
      span.text-orange-500 第一線治療如使用第一代或第二代標靶藥物，若後續出現抗藥性時，後續治療有 60 %可接續使用有健保給付的第三代標靶藥物。而如果第一線採用第三代標靶藥物治療的患者，抗藥後則有高過 77 %需接續化學治療，22.5 %雖有其他藥物但目前還未有健保給付
      | ，這些都是評估治療對於個人及家庭經濟衝擊需要提前知道的資訊。
    
    .flex.items-start.mt-5(class="flex-col space-y-5 md:space-y-0 md:flex-row")
      img(class="w-9/12 md:w-1/2 h-auto mx-auto" src="/assets/img/point-2.png")
      img(class="w-9/12 md:w-1/2 h-auto mx-auto" src="/assets/img/point-3.png")
    
</template>

<style scoped lang="sass">
.dialog-ttl
  @apply text-xl font-genjyuu-bold leading-8 text-justify

.dialog-p
  @apply mt-5 font-genjyuu-light text-gray-600 text-justify
  p
    @apply mb-3 
</style>
