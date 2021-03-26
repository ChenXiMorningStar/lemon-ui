<demo>
常规用法
</demo>
<template>
<Tabs v-model:selected="x">
  <Tab title="逃学威龙">刑事组 周星星</Tab>
  <Tab title="上学威龙">重案组 曹达华</Tab>
</Tabs>
</template>

<script lang="ts">
import Tabs from '../lib/Tabs.vue'
import Tab from '../lib/Tab.vue'
import {
  ref
} from 'vue'
export default {
  components: {
    Tabs,
    Tab
  },
  setup() {
    const x = ref('逃学威龙')
    return {
      x
    }
  }
}
</script>
