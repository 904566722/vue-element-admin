<template>
  <div class="app-container">
    <composition-list>
      <!-- 操作 -->
      <div class="operate">
        <el-button type="primary" size="small" plain>新增作品</el-button>
        <el-button type="danger" size="small" plain>删除作品</el-button>
      </div>
    </composition-list>
  </div>
</template>

<script>
import CompositionList from '../../components/composition/CompositionList'
export default {
  name: 'Composition',
  components: { CompositionList },
  data() {
    return {
      compositionList: [
        {
          id: '1',
          name: '素描',
          author: '洪惠强',
          description: '这是一张静物素描'
        },
        {
          id: '2',
          name: '素描',
          author: '洪惠强',
          description: '这是一张静物素描'
        },
        {
          id: '3',
          name: '素描',
          author: '洪惠强',
          description: '这是一张静物素描'
        },
        {
          id: '4',
          name: '素描',
          author: '洪惠强',
          description: '这是一张静物素描'
        },
        {
          id: '5',
          name: '素描',
          author: '洪惠强',
          description: '这是一张静物素描'
        },
        {
          id: '6',
          name: '素描',
          author: '洪惠强',
          description: '这是一张静物素描'
        },
        {
          id: '7',
          name: '素描',
          author: '洪惠强',
          description: '这是一张静物素描'
        }
      ]
    }
  }
}
</script>

<style scoped>
  .operate {
    margin-bottom: 20px;
  }
</style>
