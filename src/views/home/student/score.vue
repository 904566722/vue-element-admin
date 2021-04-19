<template>
  <div class="app-container">
    <grade-select @handleSelectGrade="handleSelectGrade" />

    <el-row>
      <score-chart :chart-data="lineChartData" />
    </el-row>
  </div>
</template>

<script>
import ScoreChart from './score-components/ScoreChart'
import GradeSelect from './score-components/GradeSelect'
const lineChartData = {
  firstGrade: {
    Math: [100, 99, 98, 92, 93, 95, 99, 87],
    Chinese: [80, 82, 91, 91, 80, 99, 100, 88],
    English: [88, 98, 90, 91, 94, 87, 90, 82]
  },
  secondGrade: {
    Math: [78, 68, 59, 98, 55, 80, 34, 60],
    Chinese: [60, 82, 91, 91, 80, 99, 100, 98],
    English: [88, 98, 90, 91, 94, 87, 90, 99]
  }
}
export default {
  name: 'Score',
  components: { GradeSelect, ScoreChart },
  data() {
    return {
      lineChartData: lineChartData.firstGrade
    }
  },
  methods: {
    handleSelectGrade(grade) {
      this.lineChartData = lineChartData[grade]
    }
  }
}
</script>

<style scoped>

</style>
