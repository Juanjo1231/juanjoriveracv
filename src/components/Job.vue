<template lang="pug">

  .col.s12
    h6 {{ job.company }}
      span {{ job.date }}
    position(v-for='position in job.positions' v-bind:position='position' v-bind:key='position.id')

</template>

<script>
import Position from './Position'

export default {
  name: 'job',
  props: ['job'],
  components: {
    Position
  }
}
</script>

<style lang="stylus" scoped>
h6
  font-weight bold
  font-size 1.1rem
  span
    font-weight normal
    color $strong
    font-size 0.9rem
    &::before
      content " - "
</style>