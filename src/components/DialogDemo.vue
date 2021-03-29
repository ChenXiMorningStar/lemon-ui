<template>
<h1>Dialog 对话框</h1>
<h4>模态对话框。</h4>
<Demo :component="Dialog1Demo" />
<Demo :component="Dialog2Demo" />
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
import Dialog1Demo from './Dialog1.demo.vue';
import Dialog2Demo from './Dialog2.demo.vue';
import Table from '../lib/Table.vue';
export default {
  components: {
    Demo,
    Table
  },
  setup() {
    const dataSource = [{
      parameter: 'visible(v-model)',
      instructions: '对话框是否可见',
      type: 'boolean',
      defaultValue: 'false'
    },{
      parameter: 'closeOnClickOverlay',
      instructions: '点击遮罩层是否允许关闭',
      type: 'boolean',
      defaultValue: 'true'
    },{
      parameter: 'ok',
      instructions: '点击确定回调',
      type: 'function()',
      defaultValue: '无'
    },{
      parameter: 'cancel',
      instructions: '点击取消回调',
      type: 'function()',
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
      Dialog1Demo,
      Dialog2Demo,
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
