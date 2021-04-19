<template>
  <div>
    <el-card>
      <div slot="header" class="clearfix">
        <span>作品列表</span>
      </div>
      <slot />
      <el-row :gutter="20" class="composition-list">
        <el-col
          v-for="(item, index) in compositionList"
          :key="index"
          :xs="12"
          :sm="8"
          :md="8"
          :lg="4"
          class="composition-list-item"
        >
          {{ item.name }}
          {{ item.author }}
          {{ item.description }}
        </el-col>
      </el-row>
      <el-pagination
        layout="prev, pager, next"
        :total="1000"
      />
    </el-card>
  </div>
</template>

<script>
export default {
  name: 'CompositionList',
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
.composition-list-item {
  height: 200px;
  background-color: #20a0ff;
}
</style>
