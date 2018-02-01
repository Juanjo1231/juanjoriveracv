<template lang="pug">
.secSkill
  img(v-bind:src="secSkill.image" v-bind:name="secSkill.text")
  .tooltip {{ secSkill.text }}
</template>

<script>
export default {
  name: 'secSkill',
  props: ['secSkill']
}
</script>

<style lang="stylus" scoped>
.secSkill
  position relative
  display inline-block
  margin 0.3rem
  img
    width 2.5rem
    position relative
  .tooltip
    display none
    position absolute
    top 100%
    transform translateX(-25%)
    background-color #555
    color white
    z-index 1
    padding 0.4rem
    border-radius 0.3rem
    &::after
      content ""
      position absolute
      top -10px
      left 50%
      margin-left -5px
      border-width 5px
      border-style solid
      border-color transparent transparent #555 transparent
  &:hover
    .tooltip
      display block
</style>