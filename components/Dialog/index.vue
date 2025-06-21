<script setup>
  import { useDialog, dataDialog } from "@/composables/useDialog";
  const { open, close, dialogRef } = useDialog();
  
</script>

<template lang="pug">
  div
    //- 使用 ref
    dialog#dialog(ref="dialogRef")
      button.cancel(@click="close") {{ dataDialog.cancel.btnName }}
      main
        component(:is="dataDialog.contentComponent")
  </template>


<style scoped lang="sass">
#dialog
  border: none
  width: 90%
  max-width: 860px
  position: fixed
  overflow-x: hidden
  @media screen and (max-width: 1024px)
    height: auto
    max-height: 90vh

dialog::backdrop
  background-color: rgba(#000, 0.5)

main
  overflow-y: auto
  max-height: 100%
  padding: 3rem
  
.cancel
  width: 50px
  height: 50px
  border: 0
  outline: none
  border-radius: 100%
  font-size: 1.5rem
  color: #000
  cursor: pointer
  position: absolute
  user-select: none
  top: .5rem
  right: .5rem
  z-index: 1
</style>
