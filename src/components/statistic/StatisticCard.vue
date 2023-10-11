<template>
  <a-card>
    <a-statistic v-bind="$attrs">
      <template v-for="(_, name) in $slots" #[name] :key="name">
        <slot :name="name"></slot>
      </template>
    </a-statistic>
    <a-button v-bind="{ ...props }"></a-button>
  </a-card>
</template>

<script lang="ts" setup>
import type { Props1 } from './type'
const props = withDefaults(defineProps<Props1>(), {})
// const props = withDefaults(defineProps<Props>(), {
//   title: 'Feedback',
//   value: 3,
//   precision: 2,
//   suffix: '%'
// })
</script>
