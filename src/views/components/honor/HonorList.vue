<template>
  <div>
    <el-card>
      <!-- 荣誉列表 -->
      <div class="radio">
        排序：
        <el-radio-group v-model="reverse">
          <el-radio :label="true">倒序</el-radio>
          <el-radio :label="false">正序</el-radio>
        </el-radio-group>
      </div>
      <el-timeline :reverse="reverse">
        <el-timeline-item v-for="(honor, index) in honorList" :key="index" :timestamp="honor.getTime">
          <el-card>
            {{ honor.name }}
          </el-card>
        </el-timeline-item>
      </el-timeline>
    </el-card>
  </div>
</template>

<script>
export default {
  name: 'HonorList',
  props: {
    honorList: {
      type: Array,
      default: function() {
        return []
      }
    }
  },
  data() {
    return {
      reverse: true
    }
  }
}
</script>

<style scoped>
  .radio {
    font-size: 16px;
    margin-bottom: 20px;
  }
</style>
