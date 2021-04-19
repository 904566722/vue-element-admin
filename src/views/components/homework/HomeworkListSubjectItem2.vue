<template>
  <div class="user-activity">
    <div class="post">
      <div class="user-block">
        <span class="username text-muted">{{ homeworkSubjectInfo.homeworkInfo.title }}</span>
        <span class="description">{{ homeworkSubjectInfo.homeworkInfo.publisher }}  - {{ homeworkSubjectInfo.homeworkInfo.createTime }}</span>
      </div>
      <p>{{ homeworkSubjectInfo.homeworkInfo.content }}</p>
      <ul class="list-inline">
        <li>
          <el-tag effect="dark" size="mini" type="success">{{ homeworkSubjectInfo.subject }}</el-tag>
        </li>
        <li>
          <el-tag effect="dark" size="mini" type="warning">{{ homeworkSubjectInfo.homeworkInfo.estimatedTime }}min</el-tag>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomeworkListSubjectItem2',
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

<style lang="scss" scoped>
.user-activity {
  .user-block {

    .username,
    .description {
      display: block;
      padding: 2px 0;
    }

    .username{
      font-size: 16px;
      color: #000;
    }

    :after {
      clear: both;
    }

    .img-circle {
      border-radius: 50%;
      width: 40px;
      height: 40px;
      float: left;
    }

    span {
      font-weight: 500;
      font-size: 12px;
    }
  }

  .post {
    font-size: 14px;
    border-bottom: 1px solid #d2d6de;
    margin-bottom: 15px;
    padding-bottom: 15px;
    color: #666;

    .image {
      width: 100%;
      height: 100%;
    }

    .user-images {
      padding-top: 20px;
    }
  }

  .list-inline {
    padding-left: 0;
    margin-left: -5px;
    list-style: none;

    li {
      display: inline-block;
      padding-right: 5px;
      padding-left: 5px;
      font-size: 13px;
    }

    .link-black {

      &:hover,
      &:focus {
        color: #999;
      }
    }
  }
}
</style>
