<template>
  <div class="homework-list-subject-item">
    <div class="homework-list-subject-item-header">
      {{ homeworkSubjectInfo.homeworkInfo.title }}
    </div>
    <div class="homework-list-subject-item-body">
      {{ homeworkSubjectInfo.homeworkInfo.content }}
    </div>
    <div class="homework-list-subject-item-rail">
      {{ homeworkSubjectInfo.homeworkInfo.publisher }} 发布于 {{ homeworkSubjectInfo.homeworkInfo.createTime }}
      <el-tag effect="dark" size="mini" type="success">{{ homeworkSubjectInfo.homeworkInfo.estimatedTime }}min</el-tag>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomeworkListSubjectItem',
  props: {
    homeworkSubjectInfo: {
      type: Object,
      default: () => {
        return {
          subject: '',
          homeworkInfo: {
            title: '',
            content: '',
            createTime: '',
            estimatedTime: '',
            publisher: ''
          }
        }
      }
    }
  },
  data() {
    return {
    }
  }
}
</script>

<style scoped>
  .homework-list-subject-item {
    height: 200px;
    margin-bottom: 5px;
    box-shadow: 0 2px 12px 0 rgba(0, 0, 0, 0.1);
    border-radius: 5px;
  }
  .homework-list-subject-item-body{
    height: 130px;
    padding: 10px;
  }
  .homework-list-subject-item-header {
    font-size: 18px;
    height: 30px;
    text-align: center;
    padding: 5px;
    background: #1890FF;
  }
  .homework-list-subject-item-rail {
    font-size: 12px;
  }
</style>
