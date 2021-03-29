<template>
<h1>Tabs 标签页</h1>
<h4>选项卡切换组件。</h4>
<Demo :component="Tabs1Demo" />
<div>
  <h2>API</h2>
  <Table
    :columns="columns"
    :data="dataSource"
  ></Table>
</div>
</template>

<script lang="ts">
import Demo from './Demo.vue'
import Tabs1Demo from './Tabs1.demo.vue';
import Table from '../lib/Table.vue';
export default {
  components: {
    Demo,
    Table
  },
  setup() {
    const dataSource = [{
      parameter: 'selected(v-model)',
      instructions: '当前选中的tab',
      type: 'string',
      defaultValue: '无'
    }]
    const columns = [
      {
        title: '参数',
        key: 'parameter'
      },
      {
        title: '说明',
        key: 'instructions'
      },
      {
        title: '类型',
        key: 'type'
      },
      {
        title: '默认值',
        key: 'defaultValue'
      }
    ]
    return {
      Tabs1Demo,
      dataSource,
      columns
    }
  }
}
</script>

<style lang="scss" scoped>
  h1 {
    margin-bottom: 20px;
    box-shadow: 2px 3px 3px rgb(0 0 0 / 40%);
  }
</style>
