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
    <div>{{ nums }}--{{ name }}</div>
    <button @click="sendDatas">获取子组件数据</button>
  </div>
</template>

<script>

export default {
  name: 'child1',
  // props:['msg']
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
      arr1:[3,4,5,6]
    }
  },
  methods:{
    sendDatas(){
      this.$emit('sendData',this.nums,this.name)
    }
  },
}
</script>

<style lang="less" scoped>
.child1{
  width: 100%;
  height: 200px;
  background: greenyellow;
  border: 1px solid #000;
}
</style>
