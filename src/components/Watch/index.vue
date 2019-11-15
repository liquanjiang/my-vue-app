<template>
  <div class="watch">
    <p>现在的名字{{name}}</p>
    <p>现在的{{salary}}</p>
    <p>更改前的名字{{preName}}</p>
    <p>更改之前的{{preSalary}}</p>
  </div>
</template>

<script>

/**
   props和watch（监控）的用法示例
   *
   * */
export default {
  name: 'index',
  data () {
    return {
      preName: '李大师',
      preSalary: 100000
    }
  },
  props: {
    name: {
      type: String,
      default: '李大师',
      required: true
    },
    salary: {
      type: Number,
      default: 100000,
      required: true
    }
  },
  watch: {
    name (newV, oldV) {
      this.preName = oldV
    },
    salary (newV, oldV) {
      this.preSalary = oldV
    },
    preName (newV) {
      console.log(newV)
    }
  }
}
</script>

<style scoped>
  .watch {
    height:200px;
    background:#ededed;
  }
</style>
