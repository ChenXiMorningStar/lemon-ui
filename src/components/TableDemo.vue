<template>
<h1>Table 表格</h1>
<h4>展示行列数据。</h4>
<Demo :component="Table1Demo" />
<Demo :component="Table2Demo" />
<div>
  <h2>API</h2>
  <Table
    :columns="columns"
    :data="dataSource"
  ></Table>
</div>
</template>

<script lang="ts">
import Demo from './Demo.vue';
import Table1Demo from './Table1.demo.vue';
import Table2Demo from './Table2.demo.vue';
import Table from '../lib/Table.vue';
export default {
  components: {
    Demo,
    Table
  },
  setup() {
    const dataSource = [{
      parameter: 'data',
      instructions: '数据数组',
      type: 'array',
      defaultValue: '无'
    },{
      parameter: 'columns',
      instructions: '表格列的配置项',
      type: 'array',
      defaultValue: '无'
    },{
      parameter: 'border',
      instructions: '是否显示边框',
      type: 'boolean',
      defaultValue: 'false'
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
      Table1Demo,
      Table2Demo,
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