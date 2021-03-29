<template>
<div>
  <h1>Button 按钮</h1>
  <h4>按钮用于开始一个即时操作。</h4>
  <Demo :component="Button1Demo" />
  <Demo :component="Button2Demo" />
  <Demo :component="Button3Demo" />
  <Demo :component="Button4Demo" />
  <Demo :component="Button5Demo" />
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
import Demo from "./Demo.vue";
import Button1Demo from "./Button1.demo.vue";
import Button2Demo from "./Button2.demo.vue";
import Button3Demo from "./Button3.demo.vue";
import Button4Demo from "./Button4.demo.vue";
import Button5Demo from "./Button5.demo.vue";
import Table from '../lib/Table.vue';
export default {
  components: {
    Demo,
    Table
  },
  setup() {
    const dataSource = [{
      parameter: 'theme',
      instructions: '设置按钮样式，可选值为 button text link 或者不设',
      type: 'string',
      defaultValue: 'button'
    },{
      parameter: 'size',
      instructions: '设置按钮大小，可选值为 normal big small 或者不设',
      type: 'string',
      defaultValue: 'normal'
    },{
      parameter: 'level',
      instructions: '设置按钮类型，可选值为 normal main danger 或者不设',
      type: 'string',
      defaultValue: 'normal'
    },{
      parameter: 'disabled',
      instructions: '按钮失效状态',
      type: 'boolean',
      defaultValue: 'false'
    },{
      parameter: 'loading',
      instructions: '按钮加载状态',
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
      Button1Demo,
      Button2Demo,
      Button3Demo,
      Button4Demo,
      Button5Demo,
      dataSource,
      columns
    };
  },
};
</script>

<style lang="scss" scoped>
  h1 {
    margin-bottom: 20px;
    box-shadow: 2px 3px 3px rgb(0 0 0 / 40%);
  }
</style>
