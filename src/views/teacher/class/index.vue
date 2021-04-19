<template>
  <div class="app-container">
    <class-card v-for="item in classList" :key="item" :class-info="item">
      <router-link :to="'/teacher/class/homework/publish/' + item.id" class="operate-button">
        <el-button type="primary" size="mini">
          作业发布
        </el-button>
      </router-link>
      <router-link :to="'/teacher/class/composition/' + item.id" class="operate-button">
        <el-button type="primary" size="mini">
          作品展评
        </el-button>
      </router-link>
      <router-link :to="'/teacher/class/honor/' + item.id" class="operate-button">
        <el-button type="primary" size="mini" style="margin-bottom: 15px">
          班级荣誉
        </el-button>
      </router-link>
    </class-card>
  </div>
</template>

<script>
import ClassCard from '../components/ClassCard'

export default {
  name: 'Index',
  components: { ClassCard },
  data() {
    return {
      classList: [
        {
          id: '1',
          name: '三年二班',
          peopleNumber: '50'
        },
        {
          id: '2',
          name: '三年四班',
          peopleNumber: '45'
        }
      ],
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
                publisher: '语文老师'
              }
            },
            {
              subject: '数学',
              homeworkInfo: {
                title: '这是数学作业',
                content: 'P11算术题',
                createTime: '2020.04.15 12:00:03',
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
.operate-button{
  display: block;
  margin-bottom: 5px;
}
</style>
