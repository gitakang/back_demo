
<template>
  <el-header>{{text}}</el-header>
</template>

<script>
export default {
  name: 'Header',
  data () {
    return {
      text: '这是头部'
    }
  }
}
</script>

<style lang="scss">
.el-header{
  width: 100%;
  height: 50px;
  background: white;
}
</style>
