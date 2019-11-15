<template>
  <div class="event">
    <p>我触发了{{event}}</p>
    <div class="sub-event" @click="triggerNative">触发原生事件</div>
    <div class="sub-event" @click="triggerSelf">触发自定义事件</div>
    <MyCom v-model="myValue"></MyCom>
  </div>
</template>

<script>

/**
 * event(自定义事件)、组件的v-model用法示例
 * 推荐使用kebab-case形式命名的自定义事件名
 * 一个组件上的 v-model 默认会利用名为 value 的 prop 和名为 input 的事件，
 * 但是像单选框、复选框等类型的输入控件可能会将 value 特性用于不同的目的。
 * model 选项可以用来避免这样的冲突
 * */
import MyCom from './MyComponent'
export default {
  name: 'index',
  components: {
    MyCom
  },
  data () {
    return {
      event: '原生事件',
      myValue: true
    }
  },
  props: {

  },
  methods: {
    triggerNative () {
      this.event = '原生事件'
    },
    triggerSelf () {
      this.event = '自定义事件'
      this.$emit('my-event', '123')
    }
  },
  mounted () {
  }
}
</script>

<style scoped>
.event {
  width:100%;
  height:200px;
  background:#f1f1f1;
  padding:10px 0;

}
.sub-event{
  width:120px;
  height:40px;
  background:#6a8edd;
  color:#fff;
  line-height:40px;
  border-radius:4px;
  text-align:center;
  font-size:14px;
  margin:10px auto;
  cursor:pointer;
}
</style>
