<template>
  <div class="app-container">
    <class-card v-for="item in classList" :key="item" :class-info="item">
      <router-link :to="'/teacher/student/recorded/score/' + item.id">
        <el-button type="primary" size="mini" class="operate-button">
          录入成绩
        </el-button>
      </router-link>
      <router-link :to="'/teacher/student/school/performance/' + item.id">
        <el-button type="primary" size="mini" class="operate-button" style="margin-bottom: 30px">
          在校表现
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
