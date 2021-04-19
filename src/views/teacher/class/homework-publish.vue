<template>
  <div class="app-container">
    <!-- 发布作业区域 -->
    <el-card class="homework-publish">
      <div slot="header" class="clearfix">
        <span>发布作业</span>
      </div>
      <el-form label-width="120px">
        <el-form-item label="标题">
          <el-input v-model="publishHomework.title" />
        </el-form-item>
        <el-form-item label="作业内容">
          <el-input v-model="publishHomework.content" type="textarea" />
        </el-form-item>
        <el-form-item label="估计时长(分钟)">
          <el-col :span="3">
            <el-input-number v-model="publishHomework.estimatedTime" controls-position="right" :min="1" :max="1000" placeholder="分钟" />
          </el-col>
        </el-form-item>
        <el-row>
          <el-col :span="6">
            <el-form-item label="作业时段">
              <el-select v-model="publishHomework.period">
                <el-option label="中午" value="noon" />
                <el-option label="晚上" value="night" />
                <el-option label="假期" value="vacation" />
              </el-select>
            </el-form-item>
          </el-col>
          <el-col :span="18">
            <el-form-item label="日期">
              <el-date-picker
                v-model="publishHomework.beginDate"
                type="date"
                placeholder="选择日期"
              />
              <span v-if="publishHomework.period === 'vacation'"> - </span>
              <el-date-picker
                v-if="publishHomework.period === 'vacation'"
                v-model="publishHomework.endDate"
                type="date"
                placeholder="截止日期"
              />
            </el-form-item>
          </el-col>
        </el-row>
        <el-form-item>
          <el-button type="primary">发布</el-button>
        </el-form-item>
      </el-form>
    </el-card>
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
  name: 'HomeworkPublish',
  components: {
    HomeworkListDayItem
  },
  data() {
    return {
      publishHomework: {
        title: '',
        content: '',
        estimatedTime: '',
        period: '',
        beginDate: new Date(),
        endDate: ''
      },
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
  },
  created() {
    this.setPageTitle()
  },
  methods: {
    setPageTitle() {
      const title = '作业发布'
      document.title = `${title} - ${this.$route.params.id}`
    }
  }
}
</script>

<style scoped>
  .homework-publish {
    margin-bottom: 20px;
  }
</style>
