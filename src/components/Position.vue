<template lang="pug">
  .pos-title {{ position.name[lang] }}
    li(v-for='task in position.tasks' v-bind:key="task.id") {{ task.value[lang] }}
</template>

<script>
export default {
  name: 'position',
  props: ['position', 'lang']
}
</script>

<style lang="stylus" scoped>
.pos-title
  font-weight normal
  margin 1rem 0
  text-indent 1rem
li
  margin-left 1rem
</style>