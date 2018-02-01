<template lang="pug">
.row
  .col.s2.offset-s1
    a(v-bind:href="lnk.fb" target='_blank')
      img(v-bind:src='lnk.image')
  .col.s9
    .col.s12
      a(v-bind:href="lnk.fb" target='_blank') {{ lnk.name }}
        span {{ lnk.title }}
    .col.s1
        i.material-icons phone_android
    .col.s8 {{ lnk.tel }}    

</template>

<script>
export default {
  name: 'lnk',
  props: ['lnk']
}
</script>

<style lang="stylus" scoped>
img
  max-width 4rem
  border-radius 1.5rem 0
  border 2px solid #52a4bb
a
  font-weight bold
  font-size 1.1rem
  color #5b6774
  span
    font-weight normal
    color $strong
    font-size 0.9rem
    &::before
      content " - "
</style>