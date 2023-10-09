<template>
  <div class="test">login</div>
</template>

<script setup lang="ts"></script>

<style lang="scss" scoped>
@import '@/styles/theme';

.test {
  height: 20px;
  @include useTheme {
    // 定制
    background-color: getColor(primary);
  }
}
</style>
