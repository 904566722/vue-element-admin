<template>
  <div class="homework-list-day-item">
    <div class="homework-list-day-item-date">{{ homeworkDayInfo.date }} - {{ homeworkDayInfo.timePeriod }}</div>
    <div class="homework-list-day-item-body">
      <el-row :gutter="10">
        <el-col v-for="item in homeworkDayInfo.homeworkSubjectList" :key="item" :span="8">
          <homework-list-subject-item2 :homework-subject-info="item" />
        </el-col>
      </el-row>
    </div>
  </div>
</template>

<script>
import HomeworkListSubjectItem2 from './HomeworkListSubjectItem2'
export default {
  name: 'HomeworkDayItem',
  components: {
    HomeworkListSubjectItem2
  },
  props: {
    homeworkDayInfo: {
      type: Object,
      default: () => {
        return {
          date: '',
          timePeriod: '',
          homeworkSubjectList: [
            {
              subject: '',
              homeworkInfo: {
                title: '',
                content: '',
                createTime: '',
                estimatedTime: '',
                publisher: ''
              }
            }
          ]
        }
      }
    }
  }
}
</script>

<style scoped>
  .homework-list-day-item {
    margin-bottom: 8px;
  }
  .homework-list-day-item-date {
    border-bottom: 1px solid #dfe6ec;
    padding-bottom: 10px;
    margin-bottom: 10px;
    font-weight: bold;
  }
</style>
