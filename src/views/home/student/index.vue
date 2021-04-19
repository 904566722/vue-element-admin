<template>
  <div class="app-container">
    <div v-if="user">
      <el-row :gutter="20">
        <el-col :span="6" :xs="24">
          <user-card :user="user" />
        </el-col>
        <el-col :span="18" :xs="24">
          <el-card>
            <el-tabs v-model="activeTab">
              <el-tab-pane label="成绩信息" name="score">
                <el-col :span="24">
                  <score-chart :chart-data="score" />
                </el-col>
              </el-tab-pane>
              <el-tab-pane label="在校表现" name="schoolPerformance">
                <school-performance />
              </el-tab-pane>
              <el-tab-pane label="作品记录" name="composition">
                <composition-list />
              </el-tab-pane>
            </el-tabs>
          </el-card>
        </el-col>
      </el-row>
    </div>
  </div>
</template>

<script>
import { mapGetters } from 'vuex'
import UserCard from './components/UserCard'
import SchoolPerformance from './components/SchoolPerformance'
import CompositionList from '../../components/composition/CompositionList'
import ScoreChart from './score-components/ScoreChart'

export default {
  name: 'Index',
  components: { ScoreChart, CompositionList, SchoolPerformance, UserCard },
  data() {
    return {
      user: {},
      activeTab: 'score',
      score: {
        Math: [78, 68, 59, 98, 55, 80, 34, 60],
        Chinese: [60, 82, 91, 91, 80, 99, 100, 98],
        English: [88, 98, 90, 91, 94, 87, 90, 99]
      }
    }
  },
  computed: {
    ...mapGetters([
      'name',
      'avatar',
      'roles'
    ])
  },
  created() {
    this.getUser()
  },
  methods: {
    getUser() {
      this.user = {
        name: this.name,
        role: this.roles.join(' | '),
        email: 'admin@test.com',
        avatar: this.avatar
      }
    }
  }
}
</script>

<style scoped>
</style>
