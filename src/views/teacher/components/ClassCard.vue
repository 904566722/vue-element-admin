<template>
  <div class="card-container">
    <el-card class="class-card">
      <div class="class-info">
        <div class="class-info-title"><span>{{ classInfo.name }}</span></div>
        <span class="text">人数:{{ classInfo.peopleNumber }}</span> <br>
        <span class="text">担任课程:数学</span> <br>
      </div>
      <div class="class-operations">
        <slot />
      </div>
    </el-card>
  </div>
</template>

<script>

export default {
  name: 'ClassCard',
  props: {
    classInfo: {
      type: Object,
      default: () => {
        return {
          id: '',
          name: '',
          peopleNumber: ''
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
  .card-container {
    margin-bottom: 10px;
    width: 350px;
  }
  .class-info-title{
    font-size: 32px;
  }
  .text {
    font-size: 14px;
  }
  .class-card {
  }
  .class-info {
    float: left;
    text-align: center;
    width: 200px;
  }
  .class-operations {
    float: right;
    margin-right: 20px;
  }
</style>
