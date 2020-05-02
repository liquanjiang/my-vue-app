<template>
  <div class="clock">
    <p>{{ date }}</p>
    <p>{{ name }}</p>
  </div>
</template>

<script>
import moment from 'moment'
import calendar from 'solarday2lunarday'

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
    console.log(calendar.solar2lunar())
    console.log(calendar.solar2lunar('2025-05-01'))
    console.log(calendar.isLeapYear(2022))
    console.log(calendar.getConstellation(7, 16))
    console.log(calendar.lunarYearDays(2020))
    console.log(calendar.getAllFestival(2021))

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
  .clock {
    width: 300px;
    height: 100px;
    margin: 20px auto;
  }
</style>
