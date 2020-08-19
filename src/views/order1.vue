<template>
  <div class="order1">
    <!-- order1数据：
    <span v-for="item in list" :key="item.id">{{ item }}</span>-->
    <!-- 插槽传递 -->
    <!-- <slot :list="list"></slot> -->

    <el-button type="danger" @click="dialogVisible = true">选择管理人员</el-button>
    <el-dialog title="请选择" :visible.sync="dialogVisible" width="50%">
      <div style="textAlign:center;">
        <el-checkbox-group v-model="checkedNames">
          <el-checkbox :border="true" v-for="item in adminUser" :key="item" :label="item"></el-checkbox>
        </el-checkbox-group>
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
  name: "order1",
  data() {
    return {
      list: [4, 5, 6, 7, 8],
      adminUser:['雄老师','陈老师','李老师','马老师'],
      checkedNames: [],
      dialogVisible: false,
    };
  },
  methods: {
    sendData() {
      this.$bus.$emit("send", this.checkedNames);
      this.dialogVisible = false;
    },
  },
};
</script>
<style lang="less" scoped>
.order1 {
  width: 100%;
  height: 100px;
}
</style>
