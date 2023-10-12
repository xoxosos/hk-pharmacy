<script setup lang="ts">
import { useAppStore } from '@/stores/app'
import { UploadOutlined, UserOutlined, VideoCameraOutlined } from '@ant-design/icons-vue'
import { ref } from 'vue'
const app = useAppStore()
defineOptions({
  name: 'SidebarView'
})
const isOpenSide = ref(false)
const onCollapse = (collapsed: boolean, type: string) => {
  console.log(collapsed, type)
}

const onBreakpoint = (broken: boolean) => {
  isOpenSide.value = broken
  console.log(broken)
}
const selectedKeys = ref<string[]>(['1'])
</script>
<template>
  <a-layout-sider
    breakpoint="lg"
    collapsed-width="0"
    @collapse="onCollapse"
    @breakpoint="onBreakpoint"
    :class="isOpenSide && 'fixed-side'"
  >
    <div class="logo">logo</div>
    <a-menu v-model:selectedKeys="selectedKeys" :theme="app.darkMode" mode="inline">
      <a-menu-item key="1">
        <RouterLink to="/dashboard">
          <user-outlined />
          <span class="nav-text">首页</span>
        </RouterLink>
      </a-menu-item>
      <a-menu-item key="2">
        <RouterLink to="/retail">
          <video-camera-outlined />
          <span class="nav-text">零售管理</span>
        </RouterLink>
      </a-menu-item>
      <a-menu-item key="3">
        <RouterLink to="/inventory">
          <upload-outlined />
          <span class="nav-text">库存管理</span>
        </RouterLink>
      </a-menu-item>
      <a-menu-item key="4">
        <RouterLink to="/login">
          <user-outlined />
          <span class="nav-text">nav 4</span>
        </RouterLink>
      </a-menu-item>
    </a-menu>
  </a-layout-sider>
</template>
<style lang="scss" scoped>
.logo {
  height: 32px;
  background: rgba(255, 255, 255, 0.2);
  margin: 16px;
}
.fixed-side {
  position: absolute;
  z-index: 999;
}
</style>
