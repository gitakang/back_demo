<template>
  <el-aside  :class="{'el-aside-small':small,'el-aside-medium':medium,'el-aside-big':big}">
    <ul class="aside_navs">
      <li
      v-for="(item,index) in navs"
      :key="item.id"
      @click="handleClick(index)"
      :class="{active : item.isActive}"
      >{{item.name}}</li>
    </ul>
  </el-aside>
</template>

<script>
export default {
  name: 'Aside',
  props: ['small', 'medium', 'big', 'nav'],
  data () {
    return {
      text: '这是侧边栏',
      width: '100',
      navs: this.nav
    }
  },
  methods: {
    handleClick (e) {
      let arr = this.navs.concat()
      for (let i = 0, len = arr.length; i < len; i++) {
        arr[i].isActive = false
      }
      arr[e].isActive = true
      this.navs = arr
    }
  },
  beforeCreate () {
    console.log(this)
  }
}
</script>

<style lang="scss">
  .el-aside-small{
    width: 100px !important;
    background: #000;
  }
  .el-aside-medium{
    width: 100px !important;
  }
  .el-aside-big{
    width: 200px !important;
    background: #ccc;
  }
  .aside_navs{
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: center;
    width: 100%;
    color: white;
    li{
      height: 50px;
      line-height: 50px;
      width: 100%;
      text-align: center;
    }
    .active{
      background: white;
      color: #000;
    }
  }
</style>
