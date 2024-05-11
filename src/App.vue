<script setup>
import zhCn from 'element-plus/es/locale/lang/zh-cn.mjs'
</script>

<template>
  <!-- App.vue 只需要留一个路由出口 router-view即可 -->
  <!-- 国际化处理 -->
  <el-config-provider :locale="zhCn">
    <router-view />
  </el-config-provider>
</template>

<style scoped></style>
