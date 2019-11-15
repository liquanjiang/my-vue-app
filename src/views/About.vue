<template>
  <div class="about">
    <h1>This is an about page</h1>
    <p>{{event}}</p>
    <Event @my-event="myEvent"></Event>
    <TestSlot></TestSlot>
  </div>
</template>

<script>
// @ is an alias to /src
import Event from '@/components/Event'
import TestSlot from '@/components/Slot'

export default {
  name: 'home',
  components: {
    Event,
    TestSlot
  },
  data () {
    return {
      key: {
        name: '自定义事件',
        level: '5A',
        salary: 10000000
      },
      value: '111',
      event: '原生事件'
    }
  },
  methods: {
    myEvent () {
      this.event = '自定义事件'
    }
  }
}
</script>
