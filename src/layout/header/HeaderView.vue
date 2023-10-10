<template>
  <div class="header-view">
    <!-- 全屏 -->

    <div class="header-tool-item">
      <a-tooltip placement="bottom">
        <template #title>
          {{ isFullscreen ? '退出全屏' : '开启全屏' }}
        </template>
        <span @click="toggle">
          <fullscreen-outlined v-show="!isFullscreen" />
          <fullscreen-exit-outlined v-show="isFullscreen" />
        </span>
      </a-tooltip>
    </div>

    <div class="header-tool-item">
      <a-dropdown>
        <div class="header-avatar">
          <a-avatar :src="avatar" />
          <span style="padding: 0 4px 0 8px">{{ username }} </span>
          <DownOutlined />
        </div>
        <template #overlay>
          <a-menu @click="onClick">
            <a-menu-item key="1">1st menu item</a-menu-item>
            <a-menu-item key="2">2nd menu item</a-menu-item>
            <a-menu-item key="logout">
              <span>
                退出登录
                <logout-outlined /> </span
            ></a-menu-item>
          </a-menu>
        </template>
      </a-dropdown>
    </div>
  </div>
</template>

<script setup lang="ts">
import {
  DownOutlined,
  FullscreenExitOutlined,
  FullscreenOutlined,
  LogoutOutlined
} from '@ant-design/icons-vue'
import { useFullscreen } from '@vueuse/core'
const { isFullscreen, toggle } = useFullscreen()
const username = 'username'
const avatar = 'https://xsgames.co/randomusers/avatar.php?g=pixel&key=1'
</script>

<style scoped lang="scss">
.header-view {
  float: right;
  display: flex;
  gap: 10px;
}
</style>
