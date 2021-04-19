<template>
  <div class="app-container">
    <!-- 添加荣誉 -->
    <el-card class="honor-add">
      <div slot="header" class="clearfix">
        <span>添加荣誉</span>
      </div>
      <el-form :inline="true">
        <el-form-item label="荣誉名称">
          <el-input />
        </el-form-item>
        <el-form-item label="获得时间">
          <el-date-picker type="date" placeholder="选择日期" style="width: 100%;" />
        </el-form-item>
        <el-form-item>
          <el-button type="primary">添加</el-button>
        </el-form-item>
      </el-form>
    </el-card>
    <!-- 荣誉列表 -->
    <honor-list :honor-list="honorList" />
  </div>
</template>

<script>
import HonorList from '../../components/honor/HonorList'
export default {
  name: 'Honor',
  components: { HonorList },
  data() {
    return {
      honorList: [
        {
          name: '先进班集体',
          description: '无',
          getTime: '2020-04-14'
        },
        {
          name: '优秀班集体',
          description: '无',
          getTime: '2020-05-14'
        },
        {
          name: '劳动班集体',
          description: '无',
          getTime: '2020-06-14'
        }
      ]
    }
  }
}
</script>

<style scoped>
  .honor-add {
    margin-bottom: 20px;
  }
</style>
