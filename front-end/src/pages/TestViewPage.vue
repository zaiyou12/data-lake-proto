<template>
  <Spinner :loading="store.loading" />
  <div class="view-min-width overflow-auto overscroll-none h-full">
    <template v-if="store.selectedTest == undefined">
      <InvalidTestView />
    </template>
    <template v-else>
      <TestDetailHeader />
      <TestDetails class="transform translate-y-16" />
    </template>
  </div>
</template>

<script lang="ts" setup>
import TestDetailHeader from '@/components/TestView/TestDetailHeader.vue'
import TestDetails from '@/components/TestView/TestDetails.vue'
import InvalidTestView from '@/components/TestView/InvalidTestView.vue'
import useTestViewStore from '../stores/test-view'

const store = useTestViewStore()
</script>

<style>
.view-min-width {
  min-width: 1024px;
}
</style>
