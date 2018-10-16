<template>
<el-container>
  <Aside :small="small" :nav="muen"/>
  <Aside :medium="small" />
  <el-container class="el-container-inner">
    <Header/>
    <Main class="main"/>
    <Footer/>
  </el-container>
  <Aside :big="small"/>
</el-container>
</template>
<script>
import {
  Header,
  Aside,
  Footer,
  Main
} from './components'

export default{
  components: {
    Header,
    Aside,
    Footer,
    Main
  },
  data () {
    return {
      small: true,
      muen: [
        {name: '概况', isActive: true, id: 1001},
        {name: '店铺', isActive: false, id: 1002},
        {name: '商品', isActive: false, id: 1003},
        {name: '订单', isActive: false, id: 1004},
        {name: '客户', isActive: false, id: 1005},
        {name: '数据', isActive: false, id: 1006},
        {name: '设置', isActive: false, id: 1007},
        {name: '资产', isActive: false, id: 1008},
        {name: '营销', isActive: false, id: 1009}
      ],
      childMuen: [

      ]
    }
  }
}
</script>

<style lang="scss">
.el-container{
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  .aside-left{
    background: white;
  }
  .el-container-inner{
    position:static;
    display: block;
    height: 100%;
    background: #09f;
    .main{
      height: calc(100vh - 120px);
    }
  }
 }
</style>
