<template>
  <div class="app-container">
    <el-card style="margin-bottom: 20px">
      <div slot="header">
        <span>添加资讯</span>
      </div>
      <el-form label-width="80px">
        <el-form-item label="资讯标题">
          <el-input />
        </el-form-item>
        <el-form-item label="资讯内容">
          <el-input type="textarea" />
        </el-form-item>
        <!-- 与通知不同的地方 -->
        <el-upload
          class="upload-demo"
          drag
          multiple
        >
          <i class="el-icon-upload" />
          <div class="el-upload__text">将文件拖到此处，或<em>点击上传</em></div>
        </el-upload>
        <!-- 与通知不同的地方 -->
        <el-form-item label="资讯等级">
          <el-col :span="7">
            <el-select v-model="notificationLevel" placeholder="请选择资讯等级">
              <el-option label="校级" value="schoolLevel" />
              <el-option label="年级" value="gradeLevel" />
              <el-option label="班级" value="classLevel" />
            </el-select>
          </el-col>
          <el-col :span="7">
            <el-select
              v-if="notificationLevel === 'gradeLevel'"
              v-model="belongToGrades"
              placeholder="请选择年级"
              multiple
            >
              <el-option label="一年级" value="firstGrade" />
              <el-option label="二年级" value="secondGrade" />
              <el-option label="三年级" value="thirdGrade" />
              <el-option label="四年级" value="forthGrade" />
              <el-option label="五年级" value="fifthGrade" />
              <el-option label="六年级" value="sixGrade" />
            </el-select>
          </el-col>
          <el-col :span="7">
            <el-select
              v-if="notificationLevel === 'classLevel'"
              v-model="belongToGrade"
              placeholder="请选择年级"
            >
              <el-option label="一年级" value="firstGrade" />
              <el-option label="二年级" value="secondGrade" />
              <el-option label="三年级" value="thirdGrade" />
              <el-option label="四年级" value="forthGrade" />
              <el-option label="五年级" value="fifthGrade" />
              <el-option label="六年级" value="sixGrade" />
            </el-select>
          </el-col>
          <el-col :span="7">
            <el-select
              v-if="notificationLevel === 'classLevel'"
              v-model="belongToClasses"
              placeholder="请选择年级"
              multiple
            >
              <el-option label="一年(1)班" value="firstGrade" />
              <el-option label="一年(2)班" value="secondGrade" />
              <el-option label="一年(3)班" value="thirdGrade" />
              <el-option label="一年(4)班" value="forthGrade" />
            </el-select>
          </el-col>
        </el-form-item>
      </el-form>
      <el-button type="primary" plain>发布</el-button>
    </el-card>
  </div>
</template>

<script>
export default {
  name: 'Index',
  data() {
    return {
      notificationLevel: '',
      belongToGrades: [],
      belongToGrade: '',
      belongToClasses: []
    }
  }
}
</script>

<style scoped>

</style>
