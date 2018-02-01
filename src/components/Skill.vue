<template lang="pug">
  .skill
    svg
      circle(:style='defineProgress(skill)')
</template>

<script>
export default {
  name: 'skill',
  props: ['skill'],
  methods: {
    defineProgress (skill) {
      return `stroke-dashoffset: ${skill.progress}`
    }
  }
}
</script>

<style lang="stylus" scoped>
$prof_strong = #52a4bb
$w = 100%
$c = $w / 2
$r = $c * 0.6
$l = 3.1416 * ($r * 2)

.skill
  width 5rem
  background-size 4.5rem
  background-position center
  background-repeat no-repeat
  border-radius 50%
  margin 1rem auto
  position relative
  svg
    width 100%
    height 100%
    circle
      cx $c
      cy $c
      r $r
      fill none
      stroke $prof_strong
      stroke-width 6
      stroke-dasharray $l
      animation-name prog
      animation-duration 1s
      animation-direction reverse
    
@keyframes prog
  to 
    stroke-dashoffset $l
    
</style>