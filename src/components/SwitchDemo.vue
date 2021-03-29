<template>
<div>
  <h1>Switch 开关 </h1>
  <h4>开关选择器。</h4>
  <Demo :component="Switch1Demo" />
  <Demo :component="Switch2Demo" />
</div>
<div>
  <h2>API</h2>
  <Table
    :columns="columns"
    :data="dataSource"
  ></Table>
</div>
</template>

<script lang="ts">
import Switch1Demo from './Switch1.demo.vue';
import Switch2Demo from './Switch2.demo.vue';
import Demo from './Demo.vue';
import Table from '../lib/Table.vue';
export default {
  components: {
    Demo,
    Table
  },
  setup() {
    const dataSource = [{
      parameter: 'value(v-model)',
      instructions: '指定当前是否选中',
      type: 'boolean',
      defaultValue: '无'
    },{
      parameter: 'disabled',
      instructions: '是否禁用',
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
      Switch1Demo,
      Switch2Demo,
      dataSource,
      columns
    }
  }
}
</script>

<style lang="scss" scoped>
$border-color: #d9d9d9;

.demo {
  border: 1px solid $border-color;
  margin: 16px 0 32px;

  >h2 {
    font-size: 20px;
    padding: 8px 16px;
    border-bottom: 1px solid $border-color;
  }

  &-component {
    padding: 16px;
  }

  &-actions {
    padding: 8px 16px;
    border-top: 1px dashed $border-color;
  }

  &-code {
    padding: 8px 16px;
    border-top: 1px dashed $border-color;

    >pre {
      line-height: 1.1;
      font-family: Consolas, 'Courier New', Courier, monospace;
      margin: 0;
    }
  }
}

h1 {
  margin-bottom: 20px;
  box-shadow: 2px 3px 3px rgb(0 0 0 / 40%);
}
</style>
