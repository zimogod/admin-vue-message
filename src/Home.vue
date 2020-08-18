<template>
  <div class="home">
    <!-- home组件的数据：{{ nums }}--{{ names }} -->
    <!-- <Child1>
      <template v-slot="names">
        <div>父组件接收子组件的数据为：{{ names.names }}--{{ names.nums }}</div>
      </template>
    </Child1> -->
    <!-- <Child1 @sendData="getData" :num111="nums"></Child1>
    <Child2 :info="info"></Child2> -->

    home组件
    <Page1></Page1>
  </div>
</template>

<script>
import Page1 from './client/page/page1';
import Child1 from './client/child/child1';
import Child2 from './client/child/child2';
export default {
  name: 'Home',
  components:{Child1,Child2,Page1},
  data(){
    return {
      msg:100,
      arr:[],
      nums:'',
      names:'',
      info:''
    }
  },
  methods:{
    getData(val,val1,info){
      this.nums = val;
      this.names = val1;
      this.info = info;
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
