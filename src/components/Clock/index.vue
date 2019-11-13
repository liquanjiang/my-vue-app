<template>
  <div class="clock">
    <p>{{ date }}</p>
    <p>{{ name }}</p>
  </div>
</template>

<script>
import moment from 'moment'
export default {
  name: 'index',
  inject: ['key'],
  data () {
    return {
      date: moment().format('YYYY年MM月DD日 HH：mm：ss'),
      timer: null,
      name: this.key.salary
    }
  },
  mounted () {
    this.timer = setInterval(() => {
      this.getTime()
    }, 1000)
  },

  destroyed () {
    clearInterval(this.timer)
  },

  methods: {
    getTime () {
      this.date = moment().format('YYYY年MM月DD日 HH：mm：ss')
    }
  }
}
</script>

<style scoped>
.clock{
  width:300px;
  height:100px;
  margin:20px auto;
}
</style>
