<template>
  <div>
    <el-table
      :data="studentList"
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
      <el-table-column label="性别" prop="gender" align="center">
        <template slot-scope="{row}">
          <span>{{ row.gender }}</span>
        </template>
      </el-table-column>
      <el-table-column label="姓名" prop="name" align="center">
        <template slot-scope="{row}">
          <span>{{ row.name }}</span>
        </template>
      </el-table-column>
      <!-- 插入要对学生进行的管理操作 -->
      <slot />
    </el-table>
  </div>
</template>

<script>
export default {
  name: 'StudentList',
  props: {
    studentList: {
      type: Array,
      default: () => {
        return []
      }
    }
  }
}
</script>

<style scoped>

</style>
