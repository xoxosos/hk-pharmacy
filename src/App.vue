<script setup lang="ts">
import LayoutVue from './layout/Layout.vue'

import { useAppStore } from '@/stores/app'
const app = useAppStore()
</script>

<template>
  <a-config-provider :theme="app.themeConfig">
    <LayoutVue />
  </a-config-provider>
</template>
