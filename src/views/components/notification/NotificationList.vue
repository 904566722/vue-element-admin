<template>
  <div>
    <el-card>
      <div slot="header">
        <span>通知列表</span>
      </div>
      <!-- 筛选 -->
      <div class="filter-container">
        <el-select v-model="listQuery.level" placeholder="通知等级">
          <el-option label="校级" value="schoolLevel" />
          <el-option label="年级" value="gradeLevel" />
          <el-option label="班级" value="classLevel" />
        </el-select>
        <el-select
          v-if="listQuery.level === 'gradeLevel'"
          v-model="listQuery.grade"
          placeholder="请选择年级"
        >
          <el-option label="一年级" value="firstGrade" />
          <el-option label="二年级" value="secondGrade" />
          <el-option label="三年级" value="thirdGrade" />
          <el-option label="四年级" value="forthGrade" />
          <el-option label="五年级" value="fifthGrade" />
          <el-option label="六年级" value="sixGrade" />
        </el-select>
        <el-select
          v-if="listQuery.level === 'classLevel'"
          v-model="listQuery.grade"
          placeholder="请选择年级"
        >
          <el-option label="一年级" value="firstGrade" />
          <el-option label="二年级" value="secondGrade" />
          <el-option label="三年级" value="thirdGrade" />
          <el-option label="四年级" value="forthGrade" />
          <el-option label="五年级" value="fifthGrade" />
          <el-option label="六年级" value="sixGrade" />
        </el-select>
        <el-select
          v-if="listQuery.level === 'classLevel'"
          v-model="listQuery.class"
          placeholder="请选择班级"
        >
          <el-option label="一年(1)班" value="firstGrade" />
          <el-option label="一年(2)班" value="secondGrade" />
          <el-option label="一年(3)班" value="thirdGrade" />
          <el-option label="一年(4)班" value="forthGrade" />
        </el-select>
        <el-button style="margin-left: 10px" class="filter-item" type="primary" plain>筛选</el-button>
      </div>
      <!-- 筛选 end -->
      <div>
        <notification-item v-for="item in notificationList" :key="item.id" :notification-info="item" />
      </div>
      <el-pagination
        layout="prev, pager, next"
        :total="1000"
      />
    </el-card>
  </div>
</template>

<script>
import NotificationItem from './NotificationItem'
export default {
  name: 'NotificationList',
  components: { NotificationItem },
  data() {
    return {
      listQuery: {
        level: '',
        grade: '',
        class: '',
        publisher: ''
      },
      notificationList: [
        {
          id: '1',
          title: '明天班级大扫除',
          content: '晚上让学生早点睡觉保存体力~！！！！',
          level: 'classLevel',
          classes: [
            {
              id: '1',
              name: '三年(2)班'
            },
            {
              id: '2',
              name: '三年(3)班'
            }
          ],
          publishTime: '2020-01-24 21:00：03',
          publisher: '洪惠强'
        },
        {
          id: '2',
          title: '明天开始全校停课',
          content: '停课时间:2020-03-01~2020-03-21',
          level: 'schoolLevel',
          publishTime: '2020-02-29 21:00：03',
          publisher: '洪惠强'
        },
        {
          id: '1',
          title: '明天年级大扫除',
          content: '晚上让学生早点睡觉保存体力~！！！！',
          level: 'gradeLevel',
          grades: [
            {
              id: '1',
              name: '三年级'
            },
            {
              id: '2',
              name: '四年级'
            }
          ],
          publishTime: '2020-01-24 21:00：03',
          publisher: '洪惠强'
        }
      ]
    }
  }
}
</script>

<style scoped>

</style>
