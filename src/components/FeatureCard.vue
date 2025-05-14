<template>
  <view class="feature-card">
    <view class="flex items-center mb-4">
      <text class="text-4xl mr-3">{{ icon }}</text>
      <text class="text-xl font-bold text-gray-800">{{ title }}</text>
    </view>
    <text class="text-gray-600">{{ description }}</text>
    <view class="mt-4">
      <view class="inline-block bg-blue-500 hover:bg-blue-600 text-white font-medium py-2 px-4 rounded-md transition-colors">
        Learn More
      </view>
    </view>
  </view>
</template>

<script setup lang="ts">
const props = defineProps<{
  title: string
  description: string
  icon: string
}>()
</script>
