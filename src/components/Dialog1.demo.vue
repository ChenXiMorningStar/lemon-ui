<demo>
常规用法
</demo>
<template>
<div>
  <Button @click="toggle">打开对话框</Button>
  <Dialog v-model:visible="x" :closeOnClickOverlay="false" :ok="handleOk" :cancel="handleCancel">
    <template v-slot:content>
      <strong>她开着邻居家的Toyota追着日落</strong>
      <div>被父母说是最危险的地方她都去过</div>
    </template>
    <template v-slot:title>
      <strong>加粗的标题</strong>
    </template>
  </Dialog>
</div>
</template>

<script lang="ts">
import Dialog from '../lib/Dialog.vue'
import Button from '../lib/Button.vue'
import {
  ref
} from 'vue'
import {
  openDialog
} from '../lib/openDialog'
export default {
  components: {
    Dialog,
    Button
  },
  setup() {
    const x = ref(false)
    const toggle = () => {
      x.value = !x.value
    }
    const handleOk = () => {
      return true
    }
    const handleCancel = () => {
      return true
    }
    return {
      x,
      toggle,
      handleOk,
      handleCancel
    }
  }
}
</script>
