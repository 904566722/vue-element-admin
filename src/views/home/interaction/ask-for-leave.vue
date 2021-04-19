<template>
  <div class="app-container">
    <el-card class="ask-for-leave-apply">
      <div slot="header">
        <span>请假申请</span>
      </div>
      <el-form label-width="100px">
        <el-form-item label="学号">
          <el-input v-model="formData.studentId" :disabled="true" />
        </el-form-item>
        <el-form-item label="学生姓名">
          <el-input v-model="formData.studentName" :disabled="true" />
        </el-form-item>
        <el-form-item label="家长姓名">
          <el-input v-model="formData.parentName" :disabled="true" />
        </el-form-item>
        <el-form-item label="请假事由">
          <el-input v-model="formData.reason" type="textarea" />
        </el-form-item>
        <el-row :gutter="20">
          <el-col :span="4">
            <el-form-item label="请假日期">
              <el-date-picker
                v-model="formData.date"
                type="date"
                placeholder="选择日期"
              />
            </el-form-item>
          </el-col>
        </el-row>
        <el-form-item label="当天时段">
          <el-radio v-model="formData.dayPeriod" label="morning">早上</el-radio>
          <el-radio v-model="formData.dayPeriod" label="afternoon">下午</el-radio>
          <el-radio v-model="formData.dayPeriod" label="wholeDay">全天</el-radio>
        </el-form-item>
      </el-form>
      <el-button type="primary" plain>提交</el-button>
    </el-card>
    <ask-for-leave-list />
  </div>
</template>

<script>
import AskForLeaveList from '../../components/interaction/AskForLeaveList'
export default {
  name: 'AskForLeave',
  components: { AskForLeaveList },
  data() {
    return {
      formData: {
        studentId: '22170143',
        studentName: '洪惠强',
        parentName: '大洪',
        reason: '孩子发烧',
        date: new Date(),
        dayPeriod: ''
      }
    }
  }
}
</script>

<style scoped>
.ask-for-leave-apply {
  margin-bottom: 20px;
}
</style>
