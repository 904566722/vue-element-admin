<template>
  <div class="app-container">
    <!-- 作业列表 -->
    <el-card>
      <div slot="header" class="clearfix">
        <span>作业列表</span>
      </div>
      <div class="homework-list">
        <homework-list-day-item v-for="homeworkDayItem in homeworkDayList" :key="homeworkDayItem" :homework-day-info="homeworkDayItem" />
      </div>
      <div class="block">
        <el-pagination
          layout="prev, pager, next"
          :total="1000"
        />
      </div>
    </el-card>
  </div>
</template>

<script>
import HomeworkListDayItem from '../../components/homework/HomeworkListDayItem'
export default {
  name: 'Homework',
  components: { HomeworkListDayItem },
  data() {
    return {
      homeworkDayList: [
        {
          date: '2021.04.15',
          timePeriod: 'night',
          homeworkSubjectList: [
            {
              subject: '语文',
              homeworkInfo: {
                title: '这是语文作业',
                content: 'P15生字一字3遍',
                createTime: '2020.04.15 17:00:03',
                estimatedTime: '30',
                publisher: '语文老师'
              }
            }
          ]
        },
        {
          date: '2021.04.15',
          timePeriod: 'noon',
          homeworkSubjectList: [
            {
              subject: '语文',
              homeworkInfo: {
                title: '这是语文作业',
                content: 'P10生字一字3遍',
                createTime: '2020.04.15 10:00:03',
                estimatedTime: '35',
                publisher: '语文老师'
              }
            },
            {
              subject: '数学',
              homeworkInfo: {
                title: '这是数学作业',
                content: 'P11算术题',
                createTime: '2020.04.15 12:00:03',
                estimatedTime: '50',
                publisher: '数学老师'
              }
            }
          ]
        }
      ]
    }
  }
}
</script>

<style scoped>

</style>
