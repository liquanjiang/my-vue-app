<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h2>{{ value }}</h2>
    <Clock></Clock>
    <button @click="changeProp">更改输入属性</button>
    <Computed />
    <Watch :name="name" :salary="salary"></Watch>
  </div>
</template>

<script>
import Clock from './Clock'
import Computed from './Computed'
import Watch from './Watch'
export default {
  name: 'HelloWorld',
  components: {
    Clock,
    Computed,
    Watch
  },
  inject: ['key'],
  props: {
    msg: String
  },
  data () {
    return {
      value: this.key.level,
      name: '李大师',
      salary: 1000000
    }
  },
  watch: {
    key (val1, val2) {
      console.log('v1' + JSON.stringify(val1))
      console.log('v2' + JSON.stringify(val2))
    }
  },
  methods: {
    changeProp () {
      this.name += '1'
      this.salary += 100000
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
