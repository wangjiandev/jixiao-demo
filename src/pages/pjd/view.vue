<script setup lang="ts">
const router = useRouter()

const goBack = () => {
  router.back()
}

const tableData = [
  {
    date: '张三',
    name: '80分',
    address: '',
  },
  {
    date: '李四',
    name: '80分',
    address: '',
  },
  {
    date: '王五',
    name: '80分',
    address: '',
  },
  {
    date: '赵六',
    name: '80分',
    address: '',
  },
]

const deptTableData = [
  {
    date: '办公室',
    name: '80分',
    address: '',
  },
  {
    date: '安全科',
    name: '80分',
    address: '',
  },
  {
    date: '财务科',
    name: '80分',
    address: '',
  },
]
</script>

<template>
  <div class="py-12">
    <el-page-header class="pb-4" @back="goBack">
      <template #content>
        <span class="text-large font-600 mr-3"> 王建 [2022年第一季度] 详情 </span>
      </template>
    </el-page-header>
    <el-card>
      <el-descriptions
        title="考核详情"
        direction="vertical"
        :column="4"
        :border="true"
      >
        <el-descriptions-item label="年度">
          2022年
        </el-descriptions-item>
        <el-descriptions-item label="考核批次">
          第一季度
        </el-descriptions-item>
        <el-descriptions-item label="总得分" :span="2">
          90分
        </el-descriptions-item>
        <el-descriptions-item label="品德作风（20%）">
          <el-tag size="small">
            80分
          </el-tag>
        </el-descriptions-item>
        <el-descriptions-item label="工作业绩（60%）">
          <el-tag size="small">
            90分
          </el-tag>
        </el-descriptions-item>
        <el-descriptions-item label="个人表现（20%）">
          <el-tag size="small">
            40分
          </el-tag>
        </el-descriptions-item>
        <el-descriptions-item label="奖扣分">
          <el-tag size="small">
            0分
          </el-tag>
        </el-descriptions-item>
      </el-descriptions>

      <div class="py-4 font-bold">
        个人表现-考核评议表
      </div>
      <el-table :data="tableData" :border="true" style="width: 100%">
        <el-table-column prop="date" label="姓名" width="180" />
        <el-table-column prop="name" label="分数" width="180" />
        <el-table-column prop="address" label="备注" />
      </el-table>

      <div class="py-4 font-bold">
        奖扣分项评价
      </div>
      <el-table :data="deptTableData" :border="true" style="width: 100%">
        <el-table-column prop="name" label="奖扣分数" width="180" />
        <el-table-column prop="address" label="备注" />
      </el-table>
    </el-card>
  </div>
</template>

<route lang="yaml">
meta:
  layout: admin
</route>
