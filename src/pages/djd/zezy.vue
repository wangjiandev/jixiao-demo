<script setup lang="ts">
const router = useRouter()
interface User {
  dept: string
  year: string
  batch: string
  score: string
}
const handleAdd = (index: number, row: User) => {
  router.push('/djd/djadd')
}

const handleDelete = (index: number, row: User) => {
}

const tableData: User[] = [
  {
    dept: '养护科',
    year: '2022',
    batch: '第一季度',
    score: '90',
  },
  {
    dept: '养护科',
    year: '2022',
    batch: '第二季度',
    score: '90',
  },
  {
    dept: '养护科',
    year: '2022',
    batch: '第三季度',
    score: '90',
  },
  {
    dept: '养护科',
    year: '2022',
    batch: '第四季度',
    score: '90',
  },
]

const options = ref<string[]>(['2022年', '2021年', '2020年'])
const deptOptions = ref<string[]>(['养护科', '建设科', '应急科'])
const batchOptions = ref<string[]>(['第一季度', '第二季度', '第三季度', '第四季度'])
</script>

<template>
  <div class="pt-12">
    <el-card class="box-card">
      <template #header>
        <div class="card-header">
          <span>主责主业评分</span>
        </div>
      </template>

      <el-alert title="主责主业（100分）。区分重点任务和综合工作2个二级指标，其中重点任务为70分，综合工作为30分。" type="success" :closable="false" />

      <div class="my-4">
        <el-button type="success" @click="handleAdd">
          新增科室主责主业评分
        </el-button>
        <el-select class="ml-4" placeholder="科室">
          <el-option
            v-for="item in deptOptions"
            :key="item"
            :label="item"
            :value="item"
          />
        </el-select>
        <el-select class="ml-4" placeholder="年份">
          <el-option
            v-for="item in options"
            :key="item"
            :label="item"
            :value="item"
          />
        </el-select>
        <el-select class="ml-4" placeholder="季度">
          <el-option
            v-for="item in batchOptions"
            :key="item"
            :label="item"
            :value="item"
          />
        </el-select>
      </div>
      <el-table :data="tableData" style="width: 100%">
        <el-table-column type="index" width="50" />
        <el-table-column prop="dept" label="科室名称" align="center" />
        <el-table-column prop="year" label="年份" align="center" />
        <el-table-column prop="batch" label="考核季度" align="center" />
        <el-table-column prop="score" label="主责主业得分" width="120" align="center" />
        <el-table-column label="主责主业" align="center">
          <el-table-column prop="score" label="重点工作（70分）" align="center" />
          <el-table-column prop="score" label="综合工作（30分）" align="center" />
        </el-table-column>
        <el-table-column label="操作" align="center">
          <template #default="scope">
            <el-button
              size="small"
              @click="handleDelete(scope.$index, scope.row)"
            >
              修改
            </el-button>
          </template>
        </el-table-column>
      </el-table>
    </el-card>
  </div>
</template>

<route lang="yaml">
meta:
  layout: admin
</route>
