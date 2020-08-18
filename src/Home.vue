<template>
  <div class="home">
    home组件的数据：{{ nums }}--{{ names }}
    <!-- <Child1>
      <template v-slot="names">
        <div>父组件接收子组件的数据为：{{ names.names }}--{{ names.nums }}</div>
      </template>
    </Child1> -->
    <Child1 @sendData="getData"></Child1>
    
  </div>
</template>

<script>
import Child1 from './client/child/child1';
// import Child2 from './client/child/child2';
export default {
  name: 'Home',
  components:{Child1},
  data(){
    return {
      msg:100,
      arr:[],
      nums:'',
      names:''
    }
  },
  methods:{
    getData(val,val1){
      console.log(val,val1,'===')
      this.nums = val;
      this.names = val1;
    }
  }
}
</script>
<style lang="less" scoped>
.home{
  width: 100%;
  height: 100vh;
  background: #ccc;
}
</style>
