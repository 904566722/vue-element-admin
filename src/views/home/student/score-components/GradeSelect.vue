<template>
  <div class="grade-select" style="margin-bottom: 20px">
    <el-row :gutter="10">
      <el-col
        v-for="(item, index) in gradeList"
        :key="index"
        :xs="{span:8}"
        :lg="{span:4}"
        class="grade-select-button"
      >
        <el-button @click="handleClickGrade(item.value)">{{ item.name }}</el-button>
      </el-col>
    </el-row>
  </div>
</template>

<script>
export default {
  name: 'GradeSelect',
  data() {
    return {
      gradeList: [
        {
          name: '一年级',
          value: 'firstGrade'
        },
        {
          name: '二年级',
          value: 'secondGrade'
        },
        {
          name: '三年级',
          value: 'thirdGrade'
        },
        {
          name: '四年级',
          value: 'forthGrade'
        },
        {
          name: '五年级',
          value: 'fifthGrade'
        },
        {
          name: '六年级',
          value: 'sixGrade'
        }
      ]
    }
  },
  methods: {
    handleClickGrade(grade) {
      this.$emit('handleSelectGrade', grade)
    }
  }
}
</script>

<style scoped>
  .grade-select-button {
    margin-bottom: 5px;
  }
</style>
