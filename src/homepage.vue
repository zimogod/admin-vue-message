<template>
  <div class="homepage">
    <div>
        超级管理员：
        <span>{{ list.join('、') }}</span> 
    </div>
    <order1 @send="getAdmin"></order1>
    
    <!-- <order1>
        <div slot-scope="obj">
            <span v-for="(item1,index2) in obj.list" :key="index2">{{ item1 }}</span>
        </div>
    </order1> -->
  </div>
</template>

<script>
import order1 from './views/order1';
export default {
  name: 'homepage',
  components:{order1},
  data(){
    return {
        dialogVisible: false,
        list:[]
    }
  },
  methods:{
      getAdmin(val){
          console.log(val)
          this.list = val;
      }
  } 
}
</script>
<style lang="less" scoped>
.homepage{
  width: 100%;
  height: 100vh;
//   background: #ccc;
}
</style>
