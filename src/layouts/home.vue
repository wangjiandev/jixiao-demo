<script setup lang="ts">
const router = useRouter()
</script>

<template>
  <main class="px-4 py-10 text-center text-gray-700 dark:text-gray-200">
    <div class="w-full p-2 flex justify-center items-center gap-2">
      <el-button type="primary" @click="router.push(`/djd`)">
        科室季度考核
      </el-button>
      <el-button type="success" @click="router.push(`/pjd`)">
        个人季度考核
      </el-button>
      <el-button type="info" @click="router.push(`/dnd`)">
        科室年度考核
      </el-button>
      <el-button type="warning" @click="router.push(`/pnd`)">
        个人年度考核
      </el-button>
    </div>

    <RouterView />
    <Footer />
    <div class="mt-5 mx-auto text-center opacity-75 dark:opacity-50 text-sm">
      [Home Layout]
    </div>
  </main>
</template>
