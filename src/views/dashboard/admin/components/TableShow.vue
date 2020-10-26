<template>
  <div>
    <el-table :data="tableData" border style="width: 100%;box-shadow: 0 0 10px #e2e2e2;">
      <el-table-column prop="id" label="单位名称" width="180"></el-table-column>
      <el-table-column prop="name" label="单位类型"></el-table-column>
      <el-table-column prop="price" label="联系人"></el-table-column>
      <el-table-column prop="quantity" label="联系电话"></el-table-column>
      <el-table-column label="省份"></el-table-column>
      <el-table-column label="地址"></el-table-column>
      <el-table-column label="操作"></el-table-column>
    </el-table>
  </div>
</template>

<script>
export default {
  props: {
    tableData: {
      type: Array,
      required: true
    }
  },
  filters: {
    statusText(val) {
      if (val === undefined) return
      if (val === 0) {
        return '已完成'
      } else if (val === 1) {
        return '进行中'
      } else {
        return '已取消'
      }
    },
    tagClass(val) {
      if (val === undefined) return
      if (val === 0) {
        return 'success'
      } else if (val === 1) {
        return 'warning'
      } else {
        return 'danger'
      }
    }
  }
}
</script>
