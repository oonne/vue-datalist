<template>
  <div class="datalist" v-show="show">
    <ul>
      <li v-for="item in associative" :key="item" @click="setVal(item)">
        {{item}}
      </li>
    </ul>
  </div>
</template>


<script>
export default {
  props: {
    val: {
      type: String,
      default: ''
    }, 
    setVal: {
      type: Function,
      default: () => {}
    },
    list: {
      type: Array,
      default: []
    },
    maxRow: {
      type: Number,
      default: 5
    }
  },
  computed: {
    associative () {
      let associative = this.list.filter(item => {
        if (item) {
          return item.indexOf(this.val) >= 0
        } else {
          return false
        }
      })

      if (associative.length > this.maxRow) {
        associative = associative.slice(0, this.maxRow)
      }

      return associative
    },
    show () {
      let hit = this.list.some(item => item === this.val)
      return !!this.val && this.associative.length && !hit
    }
  }
}
</script>

<style scoped>
.datalist{
  position: absolute;
  background-color: #fff;
  box-shadow: 0px 0px 2px #d4d4d4;
  width: 100%;
}

.datalist ul{
  padding: 4px 10px;
  margin: 0;
}
.datalist li{
  list-style: none;
  padding: 6px 0;
}
</style>