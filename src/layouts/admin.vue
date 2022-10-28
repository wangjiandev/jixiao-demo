<script setup lang="ts">
// const router = useRouter()
const activeIndex = ref('/')
const handleSelect = (key: string) => {
  activeIndex.value = key
}
</script>

<template>
  <div class="min-h-screen relative">
    <el-container>
      <el-header class="fixed top-0 right-0 left-0 z-10 bg-[#ffffff] dark:bg-[#121212]">
        <el-menu
          class="w-full"
          mode="horizontal"
          :ellipsis="false"
          :router="true"
          @select="handleSelect"
        >
          <el-menu-item index="/tongji">
            工作任务目标清单
          </el-menu-item>

          <el-sub-menu index="2">
            <template #title>
              季度考核
            </template>
            <el-sub-menu index="20">
              <template #title>
                科室季度考核
              </template>
              <el-menu-item index="/djd">
                考核汇总
              </el-menu-item>
              <el-menu-item index="/djd/dj">
                党的建设评分
              </el-menu-item>
              <el-menu-item index="/djd/zezy">
                主责主业
              </el-menu-item>
              <el-menu-item index="/djd/ddph">
                担当配合
              </el-menu-item>
            </el-sub-menu>
            <el-sub-menu index="300">
              <template #title>
                个人季度考核
              </template>
              <el-menu-item index="/pjd">
                考核汇总
              </el-menu-item>
              <el-menu-item index="/pjd/pdzf">
                品德作风
              </el-menu-item>
              <el-menu-item index="/pjd/gzyj">
                工作业绩
              </el-menu-item>
              <el-menu-item index="/pjd/grbx">
                个人表现
              </el-menu-item>
              <el-menu-item index="/pjd/jkf">
                奖扣分
              </el-menu-item>
            </el-sub-menu>
          </el-sub-menu>
          <el-sub-menu index="3">
            <template #title>
              年度考核
            </template>
            <el-menu-item index="/dnd">
              科室年度考核
            </el-menu-item>
            <el-menu-item index="/pnd">
              个人年度考核
            </el-menu-item>
            <el-menu-item index="/minzhu">
              民主测评
            </el-menu-item>
            <el-sub-menu index="4">
              <template #title>
                科室年度创新奖惩
              </template>
              <el-menu-item index="/djctz/upload">
                创新奖惩上报
              </el-menu-item>
              <el-menu-item index="/djctz">
                创新奖惩评分
              </el-menu-item>
            </el-sub-menu>
          </el-sub-menu>
          <el-sub-menu index="400">
            <template #title>
              自评总结
            </template>
            <el-menu-item index="/djdzj">
              科室季度工作自评总结
            </el-menu-item>
            <el-menu-item index="/pjdzj">
              个人季度工作自评总结
            </el-menu-item>
          </el-sub-menu>
        </el-menu>
      </el-header>
      <el-main class="min-h-screen">
        <RouterView />
      </el-main>
      <el-footer class="z-10 bg-[#ffffff] dark:bg-[#121212] border-gray-800/20 border-t dark:border-gray-200/20 fixed bottom-0 right-0 left-0 flex justify-center items-center">
        <Footer />
      </el-footer>
    </el-container>
  </div>
</template>

<style>
.demo {
  position: fixed;
}
</style>
