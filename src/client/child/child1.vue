<template>
  <div class="child1">
<!-- props传递 -->
    <!-- child1组件接收Home父组件传递来的数据为：{{ msg }} -->
    <!-- <div> --->

<!-- 插槽传递 -->
      <!-- <span>子组件中的数据：{{ name }}--{{ nums }}</span>
      <slot :names="name" :nums="nums"></slot>
    </div> -->

<!-- $emit() -->
    <div>{{ num111 }}</div>
    <div>子组件数据：{{ nums }}--{{ name }}</div>
    <div>哎哎哎：{{ busData }}</div>
    <!-- <button @click="sendDatas">发送子组件数据</button> -->
  </div>
</template>

<script>
// import Bus from '../../eventBus';
export default {
  name: 'child1',
  props:['num111'],
  // props:{
  //   msg:{
  //     // 校验传递来的数据类型，更严格
  //     type:Number,
  //     // 必须严传递的数据
  //     required:true,
  //     default:200
  //   },
  //   arr:{
  //     type:Array,
  //     default:() => []
  //   }
  // },
  data(){
    return {
      name:'剑哥哥！',
      nums:1000,
      arr1:[3,4,5,6],
      info:'我是child1组件数据',
      busData:'true是对的'
    }
  },
  methods:{
    // sendDatas(){
    //   // 发送数据
    //   this.$emit('sendData',this.nums,this.name)
    // }
  },
  mounted(){
    this.$bus.$emit('sendBusData',this.busData)
  },
  beforeMount(){
    this.$emit('sendData',this.nums,this.name,this.info)
  }
}
</script>

<style lang="less" scoped>
.child1{
  width: 100%;
  height: 100px;
  background: greenyellow;
  border: 1px solid #000;
}
</style>
