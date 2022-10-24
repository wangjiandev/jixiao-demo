<script setup lang="ts">
const router = useRouter()
</script>

<template>
  <main class="px-4 py-10 text-center text-gray-700 dark:text-gray-200">
    <div class="w-full p-2 flex justify-center items-center gap-2">
      <span class="px-4 py-1 bg-gray-200/50 cursor-pointer" @click="router.push(`/djd`)">科室季度考核</span>
      <span class="px-4 py-1 bg-gray-200/50 cursor-pointer" @click="router.push(`/pjd`)">个人季度考核</span>
      <span class="px-4 py-1 bg-gray-200/50 cursor-pointer" @click="router.push(`/dnd`)">科室年度考核</span>
      <span class="px-4 py-1 bg-gray-200/50 cursor-pointer" @click="router.push(`/pnd`)">个人年度考核</span>
    </div>
    <RouterView />
    <Footer />
    <div class="mt-5 mx-auto text-center opacity-75 dark:opacity-50 text-sm">
      [Home Layout]
    </div>
  </main>
</template>
