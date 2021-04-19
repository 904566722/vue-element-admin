<template>
  <div>
    <el-row :gutter="10">
      <el-col v-for="(item, index) in studentList" :key="index" :span="3">
        <el-card shadow="hover" style="margin-bottom: 10px">
          {{ item.name }}
        </el-card>
      </el-col>
    </el-row>
  </div>
</template>

<script>
export default {
  name: 'StudentTableList',
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
