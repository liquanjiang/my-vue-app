<template>
  <div>
    <input type="checkbox" :checked="checked" @change="changeValue">
  </div>
</template>

<script>
export default {
  name: 'index',
  model: {
    prop: 'checked',
    event: 'changes'
  },
  props: {
    checked: {
      type: Boolean,
      default: false
    }
  },
  methods: {
    changeValue (e) {
      this.$emit('changes', e.target.checked)
    }
  }
}
</script>

<style scoped>

</style>
