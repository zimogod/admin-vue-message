<template>
  <div class="page1">
      page1组件数据：{{ num }}
      <router-link to='/page2'>去page2</router-link>
  </div>
</template>

<script>
export default {
  name: 'page1',
  data(){
    return {
      num:200
    }
  },
  destroyed(){
    this.$bus.$emit('send',this.num)
  }
}
</script>

<style lang="less" scoped>
.page1{
  width: 100%;
  height: 100px;
  background: greenyellow;
  border: 1px solid #000;
}
</style>
