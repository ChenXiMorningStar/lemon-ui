<template>
  <table
      :class="[
          {
            'table-border': border
          }
      ]"
      class="gulu-table"
  >
    <thead>
    <tr>
      <th v-for="(item, index) in columns" :key="index">
        <div class="cell">{{ item.title }}</div>
      </th>
    </tr>
    </thead>
    <tbody>
    <tr v-for="(col, index) in data" :key="index">
      <td v-for="(colTd, tdIndex) in columns" :key="tdIndex">
        <div class="cell">{{ col[colTd.key] }}</div>
      </td>
    </tr>
    </tbody>
  </table>
</template>

<script lang="ts">
export default {
  props: {
    data: {
      type: Array,
      default() {
        return []
      }
    },
    columns: {
      type: Array,
      default() {
        return []
      }
    },
    border: {
      type: Boolean,
      default: false
    }
  }
}
</script>

<style lang="scss" scoped>
.gulu-table {
  width: 100%;
  position: relative;
  overflow: hidden;
  box-sizing: border-box;
  flex: 1;
  max-width: 100%;
  background-color: #fff;
  font-size: 14px;
  color: #606266;
  .cell {
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: normal;
    word-break: break-all;
    line-height: 23px;
    padding-left: 10px;
    padding-right: 10px;
    text-align: left;
  }
  thead {
    color: #909399;
    font-weight: 700;
    tr th {
      background: #fafafa;
      border-bottom: 1px solid #e8e8e8;
    }
  }
  td {
    border-bottom: 1px solid #e8e8e8;
  }
  td, th {
    padding: 12px 0;
    min-width: 0;
    box-sizing: border-box;
    text-overflow: ellipsis;
    vertical-align: middle;
    position: relative;
    text-align: left;
  }
  &.table-border {
    border-top: 1px solid #e8e8e8;
    border-left: 1px solid #e8e8e8;
    thead {
      border-bottom: 1px solid #e8e8e8;
    }
    td, th {
      border-right: 1px solid #e8e8e8;
    }
  }
}
</style>