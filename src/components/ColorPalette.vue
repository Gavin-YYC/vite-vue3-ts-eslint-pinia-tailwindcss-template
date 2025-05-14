<template>
  <view class="color-palette">
    <view class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 gap-4">
      <view v-for="(color, index) in colors" :key="index" @tap="selectColor(color)" class="cursor-pointer">
        <view
          class="h-16 rounded-t-lg"
          :class="color.bg"
        ></view>
        <view class="p-2 bg-gray-100 rounded-b-lg border border-t-0 border-gray-200">
          <text class="text-xs font-medium text-gray-800">{{ color.name }}</text>
          <text class="text-xs text-gray-600">{{ color.class }}</text>
        </view>
      </view>
    </view>

    <view v-if="selectedColor" class="mt-6 p-4 rounded-lg border border-gray-200">
      <text class="text-lg font-medium mb-2">Selected: {{ selectedColor.name }}</text>
      <text>Class: {{ selectedColor.class }}</text>
    </view>
  </view>
</template>

<script>
import { ref } from 'vue'

export default {
  setup() {
    const colors = [
      { name: 'Red', class: 'bg-red-500', bg: 'bg-red-500' },
      { name: 'Blue', class: 'bg-blue-500', bg: 'bg-blue-500' },
      { name: 'Green', class: 'bg-green-500', bg: 'bg-green-500' },
      { name: 'Yellow', class: 'bg-yellow-500', bg: 'bg-yellow-500' },
      { name: 'Purple', class: 'bg-purple-500', bg: 'bg-purple-500' },
      { name: 'Pink', class: 'bg-pink-500', bg: 'bg-pink-500' },
      { name: 'Indigo', class: 'bg-indigo-500', bg: 'bg-indigo-500' },
      { name: 'Gray', class: 'bg-gray-500', bg: 'bg-gray-500' }
    ]

    const selectedColor = ref(null)

    const selectColor = (color) => {
      selectedColor.value = color
    }

    return {
      colors,
      selectedColor,
      selectColor
    }
  }
}
</script>