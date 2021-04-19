<template>
  <el-card style="margin-bottom:20px;">
    <div slot="header" class="clearfix">
      <span>学生信息</span>
    </div>

    <div class="user-profile">
      <div class="box-center">
        <pan-thumb :image="user.avatar" :height="'100px'" :width="'100px'" :hoverable="false">
          <div>Hello</div>
          {{ student.name }}
        </pan-thumb>
      </div>
      <div class="box-center">
        <div class="user-name text-center">{{ student.name }}</div>
        <div class="user-role text-center text-muted">{{ student.className }}</div>
      </div>
    </div>

    <div class="user-bio">
      <!-- 学生信息 -->
      <div class="stu-info user-bio-section">
        <div class="user-bio-section-header">
          <svg-icon icon-class="link" /><span>个人资料</span>
        </div>
        <div class="user-bio-section-body">
          <span>学号:</span> {{ student.studentId }} <br>
          <span>班级:</span> {{ student.className }} <br>
          <span>性别</span> {{ student.gender == 'M' ? '男' : '女' }} <br>
          <span>出生日期:</span> {{ student.birthday }} <br>
          <span>籍贯:</span> {{ student.nativePlace }} <br>
          <span>民族:</span> {{ student.nation }} <br>
          <span>家庭地址:</span> {{ student.address }} <br>
          <span>父母联系电话:</span> {{ student.parentPhone }}
        </div>
      </div>
      <!-- other -->
      <div class="user-education user-bio-section">
        <div class="user-bio-section-header"><svg-icon icon-class="education" /><span>Education</span></div>
        <div class="user-bio-section-body">
          <div class="text-muted">
            JS in Computer Science from the University of Technology
          </div>
        </div>
      </div>

      <div class="user-skills user-bio-section">
        <div class="user-bio-section-header"><svg-icon icon-class="skill" /><span>Skills</span></div>
        <div class="user-bio-section-body">
          <div class="progress-item">
            <span>Vue</span>
            <el-progress :percentage="70" />
          </div>
          <div class="progress-item">
            <span>JavaScript</span>
            <el-progress :percentage="18" />
          </div>
          <div class="progress-item">
            <span>Css</span>
            <el-progress :percentage="12" />
          </div>
          <div class="progress-item">
            <span>ESLint</span>
            <el-progress :percentage="100" status="success" />
          </div>
        </div>
      </div>
    </div>
  </el-card>
</template>

<script>
import PanThumb from '@/components/PanThumb'

export default {
  components: { PanThumb },
  props: {
    user: {
      type: Object,
      default: () => {
        return {
          name: '',
          email: '',
          avatar: '',
          role: ''
        }
      }
    }
  },
  data() {
    return {
      student: {
        name: '洪惠强',
        studentId: '221701419',
        className: '五年一班',
        birthday: '1998.12.02',
        gender: 'M',
        nativePlace: '福建',
        nation: '汉族',
        address: '福建省漳州市漳浦县',
        parentPhone: '13859275426'
      }
    }
  }
}
</script>

<style lang="scss" scoped>
.box-center {
  margin: 0 auto;
  display: table;
}

.text-muted {
  color: #777;
}

.user-profile {
  .user-name {
    font-weight: bold;
  }

  .box-center {
    padding-top: 10px;
  }

  .user-role {
    padding-top: 10px;
    font-weight: 400;
    font-size: 14px;
  }

  .box-social {
    padding-top: 30px;

    .el-table {
      border-top: 1px solid #dfe6ec;
    }
  }

  .user-follow {
    padding-top: 20px;
  }
}

.user-bio {
  margin-top: 20px;
  color: #606266;

  span {
    padding-left: 4px;
  }

  .user-bio-section {
    font-size: 14px;
    padding: 15px 0;

    .user-bio-section-header {
      border-bottom: 1px solid #dfe6ec;
      padding-bottom: 10px;
      margin-bottom: 10px;
      font-weight: bold;
    }
  }
}
</style>
