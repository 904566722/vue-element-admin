<template>
  <div>
    <el-card>
      <div slot="header">
        <span>班级通讯录</span>
      </div>
      <el-table
        :data="teacherList"
      >
        <el-table-column prop="course" label="课程" />
        <el-table-column prop="name" label="姓名" />
        <el-table-column prop="phone" label="手机号码" />
        <el-table-column prop="email" label="邮箱" />
      </el-table>
      <el-table
        :data="studentAndParentList"
      >
        <el-table-column prop="studentId" label="学号" />
        <el-table-column prop="studentName" label="姓名" />
        <el-table-column prop="parentPhone" label="家长号码" />
        <el-table-column prop="parentName" label="家长姓名" />
        <el-table-column prop="address" label="家庭地址" />
      </el-table>
      <div class="block">
        <el-pagination
          layout="prev, pager, next"
          :total="50"
        />
      </div>
    </el-card>
  </div>
</template>

<script>
export default {
  name: 'AddressBookList',
  data() {
    return {
      studentAndParentList: [
        {
          studentId: '221701419',
          studentName: '小一',
          parentPhone: '13859275426',
          parentName: '大一',
          address: '新区学生公寓'
        },
        {
          studentId: '221701419',
          studentName: '小2',
          parentPhone: '13859275426',
          parentName: '大2',
          address: '新区学生公寓'
        },
        {
          studentId: '221701419',
          studentName: '小3',
          parentPhone: '13859275426',
          parentName: '大3',
          address: '新区学生公寓'
        },
        {
          studentId: '221701419',
          studentName: '小4',
          parentPhone: '13859275426',
          parentName: '大一',
          address: '新区学生公寓'
        },
        {
          studentId: '221701419',
          studentName: '小4',
          parentPhone: '13859275426',
          parentName: '大一',
          address: '新区学生公寓'
        }
      ],
      teacherList: [
        {
          course: '语文',
          name: '李老师',
          phone: '123432545',
          email: '1234@qq.com'
        },
        {
          course: '数学',
          name: '张老师',
          phone: '123432545',
          email: '1234@qq.com'
        },
        {
          course: '英语',
          name: '苗老师',
          phone: '123432545',
          email: '1234@qq.com'
        }
      ]
    }
  }
}
</script>

<style scoped>

</style>
