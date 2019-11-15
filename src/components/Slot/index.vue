<template>
  <div class="slot">
    <div class="sub-slot">
      {{name}}
    </div>
    <Inner>
      <template v-slot:slot2="slotProps">
        <h4>{{slotProps.data}}</h4>
      </template>
      <template v-slot:default="slotProps">
        <p class="red" >{{slotProps.data[0].name}}</p>
      </template>
      <template v-slot:slot1>
        <h4>插槽2</h4>
      </template>
    </Inner>
  </div>
</template>

<script>
import Inner from './Inner'
export default {
  name: 'index',
  components: {
    Inner
  },
  data () {
    return {
      name: 'slot测试'
    }
  },
  methods: {

  }
}
</script>

<style scoped>
.slot {
  width:100%;
  height:200px;
  background:#f1f1f1;
  padding:10px 0;
}

.sub-slot {
  width:100%;
  height:100px;
  background:#ededee;
}
.red {
  color:#f00;
  margin:0;
  padding:0;
}
</style>
