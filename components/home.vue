<template>
<div class="App">
  <div class="demo">
    <div class="demo_content">
      <input type="number" placeholder="input code" v-model="val" />
      <Datalist
        :val="val"
        :list="list"
        :setVal="onChangeCode"
      />
    </div>
  </div>
  <div class="tips">
    Input 000001
  </div>
</div>
</template>

<script>
import Datalist from './datalist.vue'

export default {
  data() {
    return {
      val: '',
      list: [
        '000001',
        '000002',
        '600000',
        '600001',
        '600002',
        '600100'
      ]
    }
  },
  components: {
    Datalist
  },
  methods: {
    onChangeCode (code) {
      this.val = code
    }
  }
}
</script>

<style>
body {
  margin: 0;
  padding: 0;
}
.App {
  width: 100vw;
  height: 100vh;
  position: fixed;
  background-color: #eee;
}

.demo{
  margin: 20px auto;
  width: 240px;
  background-color: #fff;
  border-radius: 6px;
  padding: 30px 20px;
}
.demo_content{
  position: relative;
  width: 240px;
}
input{
  width: 100%;
}
.tips{
  background-color: #fffdeb;
  border-radius: 6px;
  margin: 20px auto;
  width: 240px;
  padding: 20px;
  text-align: center;
}
</style>