<template lang="pug">
  .pos-title {{ position.name }}
    p.pos-desc {{ position.description }}
</template>

<script>
export default {
  name: 'position',
  props: ['position']
}
</script>

<style lang="stylus" scoped>
.pos-title
  font-weight normal
  margin 0
  text-indent 1rem
.pos-desc
  margin 0.3rem 0 1rem 2rem
  font-weight normal
  font-style italic
</style>