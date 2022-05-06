<template>
  <div class="app-wrapper" :class="[$store.getters.sidebarOpened ? 'openSidebar' : 'hideSidebar']">
    <!-- 左侧 menu -->
    <sidebar id="guide-sidebar" class="sidebar-container" :style="{ backgroundColor: $store.getters.cssVar.menuBg }" />
    <div class="main-container">
      <div class="fixed-header">
        <!-- 顶部的 navbar -->
        <navbar />
        <!-- tags -->
        <TagsView />
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
import TagsView from './components/TagsView/index'
import {} from 'vue'
// import variables from '@/styles/css/variables.module.scss'
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
  transition: width #{$sideBarDuration};
}

.hideSidebar .fixed-header {
  width: calc(100% - #{$hideSideBarWidth});
}
</style>
