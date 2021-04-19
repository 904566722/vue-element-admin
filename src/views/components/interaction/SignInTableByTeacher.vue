<template>
  <div>
    <el-card>
      <div slot="header">
        <span>到校签到</span>
      </div>
      <student-table-list :student-list="studentList" />
      <div class="statistics">
        <span>共计：17人</span>  <span>到校：17人</span>  <span>缺席0人</span>
      </div>
    </el-card>
  </div>
</template>

<script>
import StudentTableList from './StudentTableList'
export default {
  name: 'SignInTableByTeacher',
  components: { StudentTableList },
  data() {
    return {
      studentList: [
        {
          id: '1',
          name: '小洪'
        },
        {
          id: '1',
          name: '小洪'
        },
        {
          id: '1',
          name: '小洪'
        },
        {
          id: '1',
          name: '小洪'
        },
        {
          id: '1',
          name: '小洪'
        },
        {
          id: '1',
          name: '小洪'
        },
        {
          id: '1',
          name: '小洪'
        },
        {
          id: '1',
          name: '小洪'
        },
        {
          id: '1',
          name: '小洪'
        },
        {
          id: '1',
          name: '小洪'
        },
        {
          id: '1',
          name: '小洪'
        },
        {
          id: '1',
          name: '小洪'
        },
        {
          id: '1',
          name: '小洪'
        },
        {
          id: '1',
          name: '小洪'
        },
        {
          id: '1',
          name: '小洪'
        },
        {
          id: '1',
          name: '小洪'
        },
        {
          id: '1',
          name: '小洪'
        }
      ]
    }
  }
}
</script>

<style scoped>

</style>
