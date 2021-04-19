<template>
  <div>
    <el-card>
      <div slot="header">
        <span>请假列表</span>
      </div>
      <!-- 筛选条件 -->
      <div class="filter-container">
        <el-select v-model="listQuery.status" placeholder="申请状态" class="filter-item">
          <el-option v-for="(item, index) in statusOptions" :key="index" :label="item.name" :value="item.id" />
        </el-select>
        <el-button style="margin-left: 10px" class="filter-item" type="primary" plain>筛选</el-button>
      </div>
      <!-- 筛选条件 end -->
      <el-table
        :data="askForLeaveList"
        border
        fit
        highlight-current-row
        style="margin-bottom: 20px"
      >
        <el-table-column label="学号" prop="studentId" align="center">
          <template slot-scope="{row}">
            <span>{{ row.studentId }}</span>
          </template>
        </el-table-column>
        <el-table-column label="学生姓名" prop="studentName" align="center">
          <template slot-scope="{row}">
            <span>{{ row.studentName }}</span>
          </template>
        </el-table-column>
        <el-table-column label="家长姓名" prop="parentName" align="center">
          <template slot-scope="{row}">
            <span>{{ row.parentName }}</span>
          </template>
        </el-table-column>
        <el-table-column label="申请事由" prop="reason" align="center">
          <template slot-scope="{row}">
            <span>{{ row.reason }}</span>
          </template>
        </el-table-column>
        <el-table-column label="请假时段" prop="timePeriod" align="center">
          <template slot-scope="{row}">
            <span>{{ row.timePeriod }}</span>
          </template>
        </el-table-column>
        <el-table-column label="申请时间" prop="createdTime" align="center">
          <template slot-scope="{row}">
            <span>{{ row.createdTime }}</span>
          </template>
        </el-table-column>
        <el-table-column label="申请状态" prop="status" align="center">
          <template slot-scope="{row}">
            <el-tag v-if="row.status === '0'" type="info">未审批</el-tag>
            <el-tag v-if="row.status === '11'" type="success">同意</el-tag>
            <el-tag v-if="row.status === '12'" type="danger">拒绝</el-tag>
          </template>
        </el-table-column>
        <!-- 插入操作的插槽 -->
        <slot />
      </el-table>
      <!-- 分页 -->
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
export default {
  name: 'AskForLeaveList',
  data() {
    return {
      askForLeaveList: [
        {
          id: '1',
          studentId: '221701419',
          studentName: '小洪',
          parentName: '大洪',
          reason: '孩子发烧',
          timePeriod: '04-16 早上',
          createdTime: '04-16 07:00:03',
          status: '0'
        },
        {
          id: '2',
          studentId: '221701419',
          studentName: '小张',
          parentName: '大张',
          reason: '孩子在玩游戏',
          timePeriod: '04-16 早上',
          createdTime: '04-16 07:00:03',
          status: '12'
        },
        {
          id: '3',
          studentId: '221701419',
          studentName: '小李',
          parentName: '大李',
          reason: '孩子感冒',
          timePeriod: '04-16 早上',
          createdTime: '04-16 07:00:03',
          status: '11'
        }
      ],
      listQuery: {
        status: '',
        createdTimeFrom: '',
        createdTimeTo: ''
      },
      statusOptions: [
        {
          id: '0',
          name: '未审批'
        },
        {
          id: '11',
          name: '同意'
        },
        {
          id: '2',
          name: '拒绝'
        }
      ]
    }
  }
}
</script>

<style scoped>

</style>
