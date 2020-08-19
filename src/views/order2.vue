<template>
  <div class="order2">
     二级管理员：
    <span>{{ list.join('、') }}</span>
  </div>
</template>

<script>
export default {
  name: "order2",
//   props:{
//       list:{
//           type:Array,
//           default: ()=> ['暂无管理人员']
//       }
//   },
  data() {
    return {
      list:[]
    };
  },
  mounted(){
    //   this.$bus.$off('send');
      this.$bus.$on('send',val => {
          this.list = val;
      })
  }
};
</script>
<style lang="less" scoped>
.order2 {
  width: 100%;
  height: 100px;
}
</style>
