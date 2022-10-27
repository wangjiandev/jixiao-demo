<script setup lang="ts">
const router = useRouter()
interface User {
  dept: string
  year: string
  score: string
}

const handleEdit = (index: number, row: User) => {
  router.push('/pjd/view')
}
const handleDelete = (index: number, row: User) => {
}

const tableData: User[] = [
  {
    dept: '建设科',
    year: '2022',
    score: '90',
  },
  {
    dept: '建设科',
    year: '2022',
    score: '90',
  },
  {
    dept: '养护科',
    year: '2022',
    score: '90',
  },
  {
    dept: '路政科',
    year: '2022',
    score: '90',
  },
]

const options = ref<string[]>(['2022年', '2021年', '2020年'])
const deptOptions = ref<string[]>(['养护科', '建设科', '应急科'])
</script>

<template>
  <div class="pt-12">
    <el-card class="box-card">
      <template #header>
        <div class="card-header">
          <span>科室年度创新奖惩</span>
        </div>
      </template>
      <div class="mb-4">
        <el-select placeholder="科室">
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
      </div>
      <el-table :data="tableData" style="width: 100%">
        <el-table-column type="index" width="50" />
        <el-table-column prop="dept" label="科室名称" align="center" />
        <el-table-column prop="year" label="年份" align="center" />
        <el-table-column prop="score" label="总得分" width="120" align="center" />
        <el-table-column label="详细指标" align="center">
          <el-table-column prop="score" label="工作创新指标（10分）" align="center" />
          <el-table-column prop="score" label="工作奖惩指标（10分）" align="center" />
        </el-table-column>
        <el-table-column label="操作" align="center">
          <template #default="scope">
            <el-button size="small" @click="handleEdit(scope.$index, scope.row)">
              详情
            </el-button>
            <el-button
              size="small"
              @click="handleDelete(scope.$index, scope.row)"
            >
              打分
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
