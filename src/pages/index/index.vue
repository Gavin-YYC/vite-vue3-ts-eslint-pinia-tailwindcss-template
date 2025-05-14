<template>
  <view class="index w-full min-h-screen bg-gradient-to-b from-gray-100 to-gray-300 p-6">
    <view class="max-w-4xl mx-auto">
      <view class="text-center mb-10">
        <text class="text-3xl font-bold text-gray-800 mb-2">Tailwind Demo</text>
        <text class="text-lg text-gray-600">A simple demonstration using Tailwind CSS</text>
      </view>

      <view class="grid grid-cols-1 md:grid-cols-2 gap-6">
        <view class="bg-white rounded-lg shadow-md p-6 transition-all hover:shadow-xl">
          <text class="text-xl font-semibold text-gray-800 mb-4">Counter Component</text>
          <NumberCounter />
        </view>

        <view class="bg-white rounded-lg shadow-md p-6 transition-all hover:shadow-xl">
          <text class="text-xl font-semibold text-gray-800 mb-4">Feature Card</text>
          <FeatureCard
            title="Tailwind CSS"
            description="A utility-first CSS framework for rapidly building custom user interfaces."
            icon="🎨"
          />
        </view>
      </view>

      <view class="mt-6 bg-white rounded-lg shadow-md p-6 transition-all hover:shadow-xl">
        <text class="text-xl font-semibold text-gray-800 mb-4">Color Palette</text>
        <ColorPalette />
      </view>
    </view>
  </view>
</template>

<script setup lang="ts">
import NumberCounter from '@/components/NumberCounter.vue'
import FeatureCard from '@/components/FeatureCard.vue'
import ColorPalette from '@/components/ColorPalette.vue'
</script>
