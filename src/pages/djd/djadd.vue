<script setup lang="ts">
import { reactive } from 'vue'
const form = reactive({

})
const onSubmit = () => {
}
</script>

<template>
  <div class="py-12">
    <el-card>
      <el-form :model="form" label-width="120px">
        <el-form-item label="选择科室">
          <el-select placeholder="请选择评分科室">
            <el-option label="养护科" value="2" />
            <el-option label="建设科" value="32" />
          </el-select>
        </el-form-item>
        <el-form-item label="选择季度">
          <el-select placeholder="请选择评分季度">
            <el-option label="第一季度" value="1" />
            <el-option label="第二季度" value="2" />
            <el-option label="第三季度" value="3" />
            <el-option label="第四季度" value="4" />
          </el-select>
        </el-form-item>
        <el-form-item label="分值">
          <el-select placeholder="请选择分值">
            <el-option label="好（100分）" value="1" />
            <el-option label="较好（90分）" value="2" />
            <el-option label="一般（80分）" value="3" />
            <el-option label="差（60分）" value="4" />
          </el-select>
        </el-form-item>
        <el-form-item label="扣分原因">
          <el-input type="text" />
        </el-form-item>
        <el-form-item>
          <el-button type="primary" @click="onSubmit">
            确认
          </el-button>
        </el-form-item>
      </el-form>
    </el-card>
  </div>
</template>

<route lang="yaml">
meta:
  layout: admin
</route>
