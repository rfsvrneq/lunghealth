<script setup></script>

<template lang="pug">
div.text-gray-500
  .dialog-ttl
    p Ａ.藥物療效：
    p 我的治療選項有哪些？每個藥物的療效為何？各自有哪些強項與弱項？

  .dialog-p
    p 在正式展開第一線治療前，建議可積極與醫師討論有哪些治療選擇？各種藥物的療效為何？是否了解其各自的優勢與劣勢？因為不同的藥物用在不同的時間點，可能也會有不同的療效，這些都是可以在事前須充分了解的。
    p
      span.text-orange-500.font-genjyuu-bold 目前肺癌治療選項主要有三大類藥物：包括化學藥物、標靶藥物與免疫製劑，以及輔助性的血管抑制劑。
      | 當知道細胞型態並找到基因型態，若有基因突變，就可使用相對應的標靶藥物，若無基因突變，這時化療與免疫製劑就會是很重要的選項，而血管抑制劑則能當作輔助治療。
    p 以目前常見的 EGFR 基因突變為例，已有所謂的第一代、第二代、第三代標靶藥物，臨床上多以兩種選項進行治療，如以第二代標靶做為第一線治療，抗藥後接續第三代治療、或者第一線直接使用第三代標靶，這兩種治療策略的選擇，醫師會視病人的狀況評估。
    p 此外，部分不適合做標靶治療或免疫治療的患者，則可能採取化療或其他的治療選項，只要與醫師充分溝通討論，必能找出最適合自己的治療策略。


</template>

<style scoped lang="sass">
.dialog-ttl
  @apply text-xl font-genjyuu-bold leading-8 text-justify

.dialog-p
  @apply mt-5 font-genjyuu-light text-gray-600 text-justify
  p
    @apply mb-3 
</style>
