<template>
  <div class="inner">
    <slot name="slot2" :data="salary"></slot>
    <div class="sub-inner">
      <slot :data="list"></slot>
    </div>
    <slot name="slot1"></slot>
  </div>
</template>

<script>
export default {
  name: 'index',
  data () {
    return {
      list: [
        {
          name: 'baidu',
          value: 0
        },
        {
          name: 'tengxun',
          value: 0
        },
        {
          name: 'ali',
          value: 0
        }
      ],
      salary: 1000000
    }
  }
}
</script>

<style scoped>
.inner {
  width:300px;
  height:300px;
  background:rgba(233,111,98,0.3);
}
  .sub-inner {
    width:200px;
    height:150px;
    background:#42b983;
  }
</style>
