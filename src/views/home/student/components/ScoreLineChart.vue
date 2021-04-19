<template>
  <div :id="id" :style="{height:height,width:width}" />
</template>

<script>
import echarts from 'echarts'
export default {
  name: 'ScoreLineChart',
  props: {
    className: {
      type: String,
      default: 'chart'
    },
    id: {
      type: String,
      default: 'chart'
    },
    width: {
      type: String,
      default: '500px'
    },
    height: {
      type: String,
      default: '500px'
    },
    chartData: {
      type: Object,
      default: () => {
        return {}
      }
    }
  },
  data() {
    return {
      chart: null
    }
  },
  mounted() {
    this.initChart()
  },
  beforeDestroy() {
    if (!this.chart) {
      return
    }
    this.chart.dispose()
    this.chart = null
  },
  methods: {
    initChart() {
      this.chart = echarts.init(document.getElementById(this.id))
      this.chart.setOption({
        title: {
          text: '成绩折线图'
        },
        tooltip: {
          trigger: 'axis'
        },
        legend: {
          data: ['语文', '数学', '英语']
        },
        grid: {
          left: '2%',
          right: '2%',
          bottom: '2%',
          containLabel: true
        },
        xAxis: {
          type: 'category',
          boundaryGap: false,
          data: ['第一单元', '第二单元', '第三单元', '第四单元', '期中考试', '第五单元', '第六单元', '期末考试']
        },
        yAxis: {
          type: 'value',
          name: '成绩',
          /* y轴按比例显示 */
          scale: true
        },
        series: [
          {
            name: '语文',
            type: 'line',
            data: [96, 93, 95, 99, 95, 88, 90, 100]
          },
          {
            name: '数学',
            type: 'line',
            data: [92, 93, 94, 98, 99, 81, 92, 90]
          },
          {
            name: '英语',
            type: 'line',
            data: [90, 91, 95, 93, 90, 98, 99, 95]
          }
        ]
      })
    }
  }
}
</script>

<style scoped>

</style>
