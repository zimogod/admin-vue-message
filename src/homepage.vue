<template>
  <div class="homepage">
    <div>
        超级管理员：
        <span>{{ list.join('、') }}</span> 
    </div>
    <order1></order1>
    <order2></order2>
    <!-- <order1>
        <div slot-scope="obj">
            <span v-for="(item1,index2) in obj.list" :key="index2">{{ item1 }}</span>
        </div>
    </order1> -->
  </div>
</template>

<script>
import order1 from './views/order1';
import order2 from './views/order2';
export default {
  name: 'homepage',
  components:{order1,order2},
  data(){
    return {
        dialogVisible: false,
        list:[]
    }
  },
  mounted(){
      this.$bus.$on('send',val => {
          this.list = val;
      })
  },
}
</script>
<style lang="less" scoped>
.homepage{
  width: 100%;
  height: 100vh;
//   background: #ccc;
}
</style>
