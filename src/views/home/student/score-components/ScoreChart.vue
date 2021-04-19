<template>
  <div :class="className" :style="{height:height,width:width}" />
</template>

<script>
import echarts from 'echarts'
require('echarts/theme/macarons') // echarts theme
import resize from '../../../dashboard/admin/components/mixins/resize'

export default {
  name: 'ScoreChart',
  mixins: [resize],
  props: {
    className: {
      type: String,
      default: 'chart'
    },
    width: {
      type: String,
      default: '100%'
    },
    height: {
      type: String,
      default: '350px'
    },
    autoResize: {
      type: Boolean,
      default: true
    },
    chartData: {
      type: Object,
      required: true
    }
  },
  data() {
    return {
      chart: null
    }
  },
  watch: {
    chartData: {
      deep: true,
      handler(val) {
        this.setOptions(val)
      }
    }
  },
  mounted() {
    this.$nextTick(() => {
      this.initChart()
    })
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
      this.chart = echarts.init(this.$el, 'macarons')
      this.setOptions(this.chartData)
    },
    setOptions(chartData) {
      this.chart.setOption({
        xAxis: {
          data: ['第一单元', '第二单元', '第三单元', '第四单元', '期中考试', '第五单元', '第六单元', '期末考试'],
          boundaryGap: false,
          axisTick: {
            show: false
          }
        },
        grid: {
          left: 10,
          right: 10,
          bottom: 20,
          top: 30,
          containLabel: true
        },
        tooltip: {
          trigger: 'axis',
          axisPointer: {
            type: 'cross'
          },
          padding: [5, 10]
        },
        yAxis: {
          type: 'value',
          name: '成绩',
          /* y轴按比例显示 */
          scale: true
        },
        legend: {
          data: ['Math', 'Chinese', 'English']
        },
        series: [{
          name: 'Math', itemStyle: {
            normal: {
              color: '#409EFF',
              lineStyle: {
                color: '#409EFF',
                width: 2
              },
              label: {
                show: true
              }
            }
          },
          type: 'line',
          data: chartData.Math,
          animationDuration: 2800,
          animationEasing: 'cubicInOut'
        },
        {
          name: 'Chinese',
          type: 'line',
          itemStyle: {
            normal: {
              color: '#F56C6C',
              lineStyle: {
                color: '#F56C6C',
                width: 2
              },
              label: {
                show: true
              }
            }
          },
          data: chartData.Chinese,
          animationDuration: 2800,
          animationEasing: 'quadraticOut'
        },
        {
          name: 'English',
          type: 'line',
          itemStyle: {
            normal: {
              color: '#67C23A',
              lineStyle: {
                color: '#67C23A',
                width: 2
              },
              label: {
                show: true
              }
            }
          },
          data: chartData.English,
          animationDuration: 2800,
          animationEasing: 'quadraticOut'
        }
        ]
      })
    }
  }
}
</script>

<style scoped>

</style>
