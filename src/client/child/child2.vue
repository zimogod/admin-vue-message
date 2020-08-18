<template>
  <div class="child2">
    child2组件:{{ info }}
    <div>通过eventBus传递来的数据：{{ busData }}</div>
  </div>
</template>

<script>
// import Bus from '../../eventBus';
export default {
  name: 'child2',
  props:['info'],
  data(){
    return {
      busData:null
    }
  },
  created(){
    this.$bus.$on('sendBusData',(val) =>{
      console.log(val)
      this.busData = val;
    })
  }
}
</script>

<style lang="less" scoped>
.child2{
  width: 100%;
  height: 100px;
  background: red;
  border: 1px solid #000;
}
</style>
