<template>
  <div class="app-container">
    <ask-for-leave-list>
      <!-- 插入操作 -->
      <el-table-column label="操作" align="center">
        <template>
          <el-button type="primary" size="mini">同意</el-button>
          <el-button type="danger" size="mini">拒绝</el-button>
        </template>
      </el-table-column>
    </ask-for-leave-list>
  </div>
</template>

<script>
import AskForLeaveList from '../../components/interaction/AskForLeaveList'
export default {
  name: 'AskForLeave',
  components: { AskForLeaveList }
}
</script>

<style scoped>

</style>
