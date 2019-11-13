<template>
  <div class="home">
    <HelloWorld msg="Vue App" />
    <p>home页{{key.salary}}</p>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'home',
  components: {
    HelloWorld
  },
  data () {
    return {
      key: {
        name: '李大师',
        level: '5A',
        salary: 10000000
      },
      value: '111'
    }
  },
  provide () {
    return {
      key: this.key
    }
  },
  methods: {
    changeMsg () {
      let { salary } = this.key
      const obj = Object.assign(this.key, { salary: salary += 1000 });
      console.log(obj)
      this.$set(this.key, obj)
    }
  }
}
</script>
