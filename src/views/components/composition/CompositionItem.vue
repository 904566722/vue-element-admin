<template>
  <div class="composition-item">
    <!-- 作品图片 -->
    <div class="composition-item-picture" />
    <!-- 作品信息 -->
    <div class="composition-item-info">
      <span>{{ compositionInfo.name }}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CompositionItem',
  props: {
    compositionInfo: {
      type: Object,
      default: () => {
        return {
          id: '',
          name: '',
          author: '',
          description: ''
        }
      }
    }
  }
}
</script>

<style scoped>
  .composition-item{
    background-color: #42b983;
    width: 200px;
    height: 200px;
    margin-right: 20px;
    margin-bottom: 20px;
  }
</style>
