<script setup lang="ts">
interface User {
  dept: string
  year: string
  batch: string
  zongjie: string
}

const tableData: User[] = [
  {
    dept: '养护科',
    year: '2022',
    batch: '第一季度',
    zongjie: '以年终总结、半年总结和季度总结最为常见和多用。就其内容而言，工作总结就是把一个时间段的工作进行一次全面系统的总检查、总评价、总分析、总研究，并分析成绩的不足，从而得出引以为戒的经验。总结是应用写作的一种，是对已经做过的工作进行理性的思考。总结与计划是相辅相成的，要以工作计划为依据，订计划总是在总结经验的基础上进行的。其间有一条规律：计划——实践——总结——再计划——再实践——再总结。',
  },
  {
    dept: '养护科',
    year: '2022',
    batch: '第二季度',
    zongjie: '以年终总结、半年总结和季度总结最为常见和多用。就其内容而言，工作总结就是把一个时间段的工作进行一次全面系统的总检查、总评价、总分析、总研究，并分析成绩的不足，从而得出引以为戒的经验。总结是应用写作的一种，是对已经做过的工作进行理性的思考。总结与计划是相辅相成的，要以工作计划为依据，订计划总是在总结经验的基础上进行的。其间有一条规律：计划——实践——总结——再计划——再实践——再总结。',
  },
  {
    dept: '建设科',
    year: '2022',
    batch: '第一季度',
    zongjie: '以年终总结、半年总结和季度总结最为常见和多用。就其内容而言，工作总结就是把一个时间段的工作进行一次全面系统的总检查、总评价、总分析、总研究，并分析成绩的不足，从而得出引以为戒的经验。总结是应用写作的一种，是对已经做过的工作进行理性的思考。总结与计划是相辅相成的，要以工作计划为依据，订计划总是在总结经验的基础上进行的。其间有一条规律：计划——实践——总结——再计划——再实践——再总结。',
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
          <span>科室季度工作自评总结</span>
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
        <el-table-column prop="dept" label="科室名称" align="center" width="150" />
        <el-table-column prop="year" label="年份" align="center" width="150" />
        <el-table-column prop="batch" label="季度" align="center" width="150" />
        <el-table-column prop="zongjie" label="工作总结" />
        <el-table-column label="操作" align="center" width="150">
          <el-button size="small">
            详情
          </el-button>
        </el-table-column>
      </el-table>
    </el-card>
  </div>
</template>

<route lang="yaml">
meta:
  layout: admin
</route>
