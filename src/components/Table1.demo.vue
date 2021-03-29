<demo>
基本用法
</demo>
<template>
  <Table
    :columns="columns"
    :data="dataSource"
  ></Table>
</template>

<script lang="ts">
import Table from '../lib/Table.vue'
export default {
  components: { Table },
  setup() {
    const dataSource = [{
      production: '夜曲',
      name: '周杰伦',
      album: '十一月的萧邦'
    },{
      production: '夜的第七章',
      name: '周杰伦',
      album: '依然范特西'
    },{
      production: '止战之殇',
      name: '周杰伦',
      album: '七里香'
    },{
      production: '以父之名',
      name: '周杰伦',
      album: '叶惠美'
    }]
    const columns = [
      {
        title: '作品',
        key: 'production'
      },
      {
        title: '歌手',
        key: 'name'
      },
      {
        title: '专辑',
        key: 'album'
      }
    ]
    return {
      dataSource,
      columns
    }
  }
}
</script>