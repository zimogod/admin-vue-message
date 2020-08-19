<template>
  <div class="order1">
    <!-- order1数据：
    <span v-for="item in list" :key="item.id">{{ item }}</span> -->
<!-- 插槽传递 -->
    <!-- <slot :list="list"></slot> -->

    <el-button type="text" @click="dialogVisible = true">选择管理人员</el-button>
    <el-dialog
        title="请选择"
        :visible.sync="dialogVisible"
        width="50%"
        >
        <div>
            <input type="checkbox" id="jack" value="李雄" v-model="checkedNames">
            <label for="jack">李雄</label>
            <input type="checkbox" id="john" value="陈铁柱" v-model="checkedNames">
            <label for="john">陈铁柱</label>
            <input type="checkbox" id="mike" value="李保龙" v-model="checkedNames">
            <label for="mike">李保龙</label>
        </div>
        <span slot="footer" class="dialog-footer">
            <el-button @click="dialogVisible = false">取 消</el-button>
            <el-button type="primary" @click="sendData">确 定</el-button>
        </span>
    </el-dialog>
  </div>
</template>

<script>
export default {
  name: 'order1',
  data(){
    return {
       list:[4,5,6,7,8],
       checkedNames: [],
       dialogVisible:false
    }
  },
  methods:{
    sendData(){
      this.$emit('send',this.checkedNames);
      this.dialogVisible = false;
    }
  },
}
</script>
<style lang="less" scoped>
.order1{
  width: 100%;
  height: 100px;
}
</style>
