<template>
  <div>dashboard</div>
  <div style="padding: 30px">
    <a-row :gutter="16">
      <a-col :span="12">
        <StatisticCard :value-style="{ color: 'red' }">
          <template #prefix>
            <arrow-up-outlined />
          </template>
        </StatisticCard>
      </a-col>
      <a-col :span="12">
        <StatisticCard>
          <template #prefix>
            <arrow-down-outlined />
          </template>
        </StatisticCard>
      </a-col>
    </a-row>
  </div>
</template>

<script setup lang="ts">
import StatisticCard from '@/components/statistic/StatisticCard.vue'
import { ArrowDownOutlined, ArrowUpOutlined } from '@ant-design/icons-vue'
</script>

<style lang="scss" scoped></style>
