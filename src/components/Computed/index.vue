<template>
  <div class="computed">
    <div>
      <p>排骨价格{{price}}元/斤</p>
      <p>排骨重量{{weight}}斤</p>
      <p>排骨总价{{money}}元</p>
      <div class="circle-div">
        <span class="sp-circle"></span>
      </div>
    </div>
    <div class="button" @click="changeMoney">我要涨价</div>
  </div>
</template>

<script>

/**
   data和computed（计算属性）的用法示例
   *
   * */
export default {
  name: 'index',
  data () {
    return {
      name: 'computed',
      price: 29.88,
      weight: 5,
      newPrice: 40
    }
  },
  computed: {
    money: {
      get () {
        return this.price * this.weight
      },
      // 在computed中设置set方法的尝试
      set (newValue) {
        this.price = this.newPrice
        this.weight = 5
      }
    }
  },
  methods: {
    changeMoney () {
      this.money = 200
    }
  }
}
</script>

<style scoped>
  .computed {
    height:200px;
    background:#f1f1f1;
  }
  .button{
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
  .circle-div {
    background:#f1f111
  }
  /* Spinner Circle Rotation */
  .sp-circle {
    border: 4px rgba(98, 98, 198, 0.25) solid;
    border-top: 4px rgb(98,98,198) solid;
    border-radius: 50%;
    -webkit-animation: spCircRot 1s infinite linear;
    animation: spCircRot 1s infinite linear;
    width:20px;
    height:20px;
    display:block;
  }

  @-webkit-keyframes spCircRot {
    from {
      -webkit-transform: rotate(0deg);
    }
    to {
      -webkit-transform: rotate(359deg);
    }
  }
  @keyframes spCircRot {
    from {
      transform: rotate(0deg);
    }
    to {
      transform: rotate(359deg);
    }
  }
</style>
