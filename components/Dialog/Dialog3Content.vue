<script setup></script>

<template lang="pug">
div.text-gray-500
  .dialog-ttl
    p Ｃ.抗藥後的治療：
    p 一旦發生抗藥性後還有哪些治療選擇？如何達到最佳存活期？

  .dialog-p
    p 治療一定會產生抗藥性，只是每個人出現的時間點不太一樣。一旦出現抗藥性，也等於病情出現擴大或惡化；基本上，這時會請病人重新做病理切片，並送基因檢測如 NGS 次世代基因檢測（健保已有補助），找出抗藥基因機轉，在與醫療團隊討論後續的治療方向。

    p 根據亞洲國際大型研究 GioSwinG 統計，
      span.text-orange-500 一線採用二代標靶接續三代標靶進行治療，整體存活期可超過 5 年( 63.5 個月)，即便採第二代標靶藥物接續化療，整體存活期也可超過 4年( 50 個月)。由此可見，若 EGFR 基因突變的治療策略採一線接一線治療，有機會達較長的整體存活期。
    
    p 若是單看現階段標靶藥物用在亞洲族群數據可發現，第一線使用第三代標靶藥物約 16-18個月後會產生抗藥性，由於三代標靶藥物抗藥後，其腫瘤微環境更為複雜，因此使得後續能使用的標靶藥物相對少(且目前尚未給付)，或是以化學治療為主；因此鼓勵初確診的病患及家屬，因有計畫的與醫師討論及通盤了解自己的接續治療計畫。

</template>

<style scoped lang="sass">
.dialog-ttl
  @apply text-xl font-genjyuu-bold leading-8 text-justify

.dialog-p
  @apply mt-5 font-genjyuu-light text-gray-600 text-justify
  p
    @apply mb-3 
</style>
