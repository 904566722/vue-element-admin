<template>
  <div class="app-container">
    <el-select v-model="belongToExam" placeholder="属于哪场考试" style="margin-bottom: 20px">
      <el-option
        v-for="item in examList"
        :key="item.id"
        :label="item.title + '(' + item.acadYearTerm + ')'"
        :value="item.title"
      />
    </el-select>
    <!-- 录入成绩的表格 -->
    <student-list :student-list="studentList">
      <el-table-column label="成绩" prop="score" align="center">
        <template slot-scope="{row}">
          <el-input v-model="row.score" />
        </template>
      </el-table-column>
    </student-list>
    <el-button type="primary" size="small">录入</el-button>
  </div>
</template>

<script>
import StudentList from './components/StudentList'
export default {
  name: 'RecordedScore',
  components: { StudentList },
  data() {
    return {
      /* 这些成绩属于哪场考试 */
      belongToExam: {
      },
      examList: [
        {
          id: '1',
          title: '第一单元语文考试',
          acadYearTerm: '五年级上学期'
        },
        {
          id: '2',
          title: '第二单元语文考试',
          acadYearTerm: '五年级上学期'
        },
        {
          id: '3',
          title: '第三单元语文考试',
          acadYearTerm: '五年级上学期'
        }
      ],
      studentList: [
        {
          studentId: '221701419',
          name: '洪惠强',
          gender: 'M',
          score: ''
        },
        {
          studentId: '221701420',
          name: '洪小儿',
          gender: 'F',
          score: ''
        },
        {
          studentId: '221701421',
          name: '洪小三',
          gender: 'M',
          score: ''
        },
        {
          studentId: '221701422',
          name: '洪笑死',
          gender: 'M',
          score: ''
        }
      ]
    }
  }
}
</script>

<style scoped>

</style>
