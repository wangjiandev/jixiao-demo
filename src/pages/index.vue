<script setup lang="ts">
</script>

<template>
  <div class="pt-12 flex flex-col gap-4 justify-center items-center h-32 font-bold text-5xl bg-gradient-to-r from-[#42d392] to-[#647eff] bg-clip-text text-transparent">
    督办系统新增绩效功能界面原型演示
  </div>
  <el-divider>
    淄博定制版
  </el-divider>
  <div class="flex gap-4 justify-center items-center">
    <el-card class="w-120">
      <ListLatestDept />
    </el-card>
    <el-card class="w-120">
      <ListLatest />
    </el-card>
  </div>
</template>

<route lang="yaml">
meta:
  layout: admin
</route>
