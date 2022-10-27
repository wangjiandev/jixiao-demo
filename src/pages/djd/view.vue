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

const deptTableData2 = [
  {
    date: '养护科',
    name: '80分',
    address: '',
  },
  {
    date: '建设科',
    name: '80分',
    address: '',
  },
  {
    date: '应急科',
    name: '80分',
    address: '',
  },
  {
    date: '建设科',
    name: '80分',
    address: '',
  },
]
</script>

<template>
  <div class="py-12">
    <el-page-header class="pb-4" @back="goBack">
      <template #content>
        <span class="text-large font-600 mr-3"> 养护科 [2022年第一季度] 详情 </span>
      </template>
    </el-page-header>
    <el-card>
      <el-descriptions
        title="考核详情"
        direction="vertical"
        :column="4"
        border
      >
        <el-descriptions-item label="年度">
          2022年
        </el-descriptions-item>
        <el-descriptions-item label="考核季度">
          第一季度
        </el-descriptions-item>
        <el-descriptions-item label="总得分" :span="2">
          90分
        </el-descriptions-item>
        <el-descriptions-item label="党的建设（20%）">
          <el-tag size="small">
            60分
          </el-tag>
        </el-descriptions-item>
        <el-descriptions-item label="主责主业（60%）" :span="2">
          <el-tag size="small">
            60分
          </el-tag>
        </el-descriptions-item>
        <el-descriptions-item label="担当配合（20%）" :span="2">
          <el-tag size="small">
            60分
          </el-tag>
        </el-descriptions-item>
      </el-descriptions>

      <el-descriptions
        title="主责主业详情"
        direction="vertical"
        :column="4"
        class="mt-4"
        border
      >
        <el-descriptions-item label="重点工作（70分）">
          <el-tag size="small">
            68分
          </el-tag>
        </el-descriptions-item>
        <el-descriptions-item label="综合工作（30分）">
          <el-tag size="small">
            24分
          </el-tag>
        </el-descriptions-item>
      </el-descriptions>

      <div class="py-4 font-bold">
        重点工作-领导评议
      </div>
      <el-table :data="tableData" border style="width: 100%">
        <el-table-column prop="date" label="姓名" width="180" />
        <el-table-column prop="name" label="分数" width="180" />
        <el-table-column prop="address" label="备注" />
      </el-table>

      <div class="py-4 font-bold">
        综合工作
      </div>
      <el-table :data="deptTableData" border style="width: 100%">
        <el-table-column prop="date" label="科室" width="180" />
        <el-table-column prop="name" label="分数" width="180" />
        <el-table-column prop="address" label="备注" />
      </el-table>

      <div class="py-4 font-bold">
        配合担当
      </div>
      <el-table :data="deptTableData2" border style="width: 100%">
        <el-table-column prop="date" label="科室" width="180" />
        <el-table-column prop="name" label="分数" width="180" />
        <el-table-column prop="address" label="备注" />
      </el-table>
    </el-card>
  </div>
</template>

<route lang="yaml">
meta:
  layout: admin
</route>
