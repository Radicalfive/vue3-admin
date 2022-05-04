<template>
  <div class="app-wrapper">
    <!-- 左侧 menu -->
    <sidebar class="sidebar-container" :style="{ backgroundColor: variables.menuBg }" />
    <div class="main-container">
      <div class="fixed-header">
        <!-- 顶部的 navbar -->
        <navbar />
      </div>
      <!-- 内容区 -->
      <AppMain />
    </div>
  </div>
</template>

<script setup>
import Navbar from './components/Navbar/index'
import Sidebar from './components/Sidebar/index'
import AppMain from './components/AppMain/index'
import {} from 'vue'
import variables from '@/styles/css/variables.module.scss'
</script>

<style lang="scss" scoped>
@import '~@/styles/css/mixins.scss';
@import '~@/styles/css/variables.module.scss';

.app-wrapper {
  @include clearfix;
  position: relative;
  height: 100%;
  width: 100%;
}

.fixed-header {
  position: fixed;
  top: 0;
  right: 0;
  z-index: 9;
  width: calc(100% - #{$sideBarWidth});
}
</style>
