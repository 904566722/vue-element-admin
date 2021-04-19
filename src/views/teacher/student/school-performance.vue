<template>
  <div class="app-container">
    <el-select v-model="belongToAcadYearTeam" placeholder="属于哪一学期" style="margin-bottom: 20px">
      <el-option
        v-for="item in acadYearTermList"
        :key="item.id"
        :label="item.name"
        :value="item.name"
      />
    </el-select>
    <student-list :student-list="studentList">
      <el-table-column label="操作" align="center" width="200px">
        <template slot-scope="{row}">
          <el-button type="primary" size="mini" @click="handleEvaluate(row)">编辑</el-button>
        </template>
      </el-table-column>
    </student-list>
    <!-- 评价对话框 -->
    <el-dialog :visible.sync="dialogFormVisible">
      <el-form ref="dataForm" :rules="rules" :model="temp" label-position="left" label-width="70px" style="width: 400px; margin-left:50px;">
        <el-form-item label="姓名" prop="name">
          <el-input v-model="temp.name" :disabled="true" />
        </el-form-item>
        <el-form-item label="评星级">
          <el-rate v-model="temp.starNumber" :colors="['#99A9BF', '#F7BA2A', '#FF9900']" :max="10" style="margin-top:8px;" />
        </el-form-item>
        <el-form-item label="评语">
          <el-input v-model="temp.evaluate" :autosize="{ minRows: 3, maxRows: 6}" type="textarea" placeholder="输入评语" />
        </el-form-item>
      </el-form>
      <div slot="footer" class="dialog-footer">
        <el-button @click="dialogFormVisible = false">
          取消
        </el-button>
        <el-button type="primary" @click="dialogFormVisible = false">
          确认
        </el-button>
      </div>
    </el-dialog>
  </div>
</template>

<script>
import StudentList from './components/StudentList'
export default {
  name: 'SchoolPerformance',
  components: { StudentList },
  data() {
    return {
      belongToAcadYearTeam: '',
      dialogFormVisible: false,
      temp: {
        studentId: undefined,
        name: '',
        starNumber: '',
        evaluate: '',
        status: ''
      },
      acadYearTermList: [
        {
          id: '1',
          name: '一年级上学期'
        },
        {
          id: '2',
          name: '一年级下学期'
        },
        {
          id: '3',
          name: '二年级上学期'
        }
      ],
      studentList: [
        {
          studentId: '221701419',
          name: '洪惠强',
          gender: 'M',
          score: '',
          starNumber: '',
          evaluate: '',
          status: ''
        },
        {
          studentId: '221701420',
          name: '洪小儿',
          gender: 'F',
          score: '',
          starNumber: '',
          evaluate: '',
          status: ''
        },
        {
          studentId: '221701421',
          name: '洪小三',
          gender: 'M',
          score: '',
          starNumber: '',
          evaluate: '',
          status: ''
        },
        {
          studentId: '221701422',
          name: '洪笑死',
          gender: 'M',
          score: '',
          starNumber: '',
          evaluate: '',
          status: ''
        }
      ]
    }
  },
  methods: {
    /**
     * 打开评价对话框
     * @param row 一行数据
     */
    handleEvaluate(row) {
      this.temp = Object.assign({}, row)
      this.dialogFormVisible = true
    }
  }
}
</script>

<style scoped>

</style>
