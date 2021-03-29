<demo>
一键打开
</demo>
<template>
<div>
  <Button @click="showDialog">打开对话框</Button>
</div>
</template>

<script lang="ts">
import Button from '../lib/Button.vue'
import {
  ref,
  h
} from 'vue'
import {
  openDialog
} from '../lib/openDialog'
export default {
  components: {
    Button
  },
  setup() {
    const showDialog = () => {
      openDialog({
        title: h('strong', {}, '标题'),
        content: '今晚演出的rapper算得上是她最喜欢 她走到吧台先点了一杯whisky酸',
        ok() {
          console.log('ok')
        },
        cancel() {
          console.log('cancel')
        }
      })
    }
    return {
      showDialog
    }
  }
}
</script>
