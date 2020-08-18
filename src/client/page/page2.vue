<template>
  <div class="page2">
      page2组件数据：{{ num }}
  </div>
</template>

<script>
export default {
  name: 'page2',
  data(){
    return {
        num:''
    }
  },
  beforeCreate(){
    // 接收数据
    this.$bus.$off('send');
    this.$bus.$on('send',(num) =>{
      console.log(num)
      this.num = num;
    })
  }
}
</script>

<style lang="less" scoped>
.page2{
  width: 100%;
  height: 100px;
  background: gold;
  border: 1px solid #000;
}
</style>
