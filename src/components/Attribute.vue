<template lang="pug">

.col.s5.offset-s1.qua
        svg.marked
          path.line
        div {{ attr.val }}

</template>

<script>
export default {
  name: 'attribute',
  props: ['attr']
}
</script>

<style lang="stylus" scoped>
.marked
  width 35px
  height 35px
  display inline-block
  .line
    fill none
    stroke #00487C
    stroke-width 5
    stroke-linecap round
    stroke-linejoin round
    stroke-dasharray 27
    stroke-dashoffset 27
    d path("M8,20 L15,25 25,10")
    animation-name check
    animation-duration 0.5s
    animation-iteration-count 1
    animation-fill-mode forwards
    animation-timing-function cubic-bezier(0.8, 0, 1, 1)
    animation-delay 0.8s

@keyframes check
  to
    stroke-dashoffset 0
    
.qua
  display flex
  div
    padding-top 0.5rem
</style>