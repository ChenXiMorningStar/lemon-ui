<template>
<h1>Table 表格</h1>
<h4>展示行列数据。</h4>
<Demo :component="Table1Demo" />
<Demo :component="Table2Demo" />
</template>

<script lang="ts">
import Demo from './Demo.vue';
import Table1Demo from './Table1.demo.vue';
import Table2Demo from './Table2.demo.vue';
export default {
  components: {
    Demo
  },
  setup() {
    return {
      Table1Demo,
      Table2Demo
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