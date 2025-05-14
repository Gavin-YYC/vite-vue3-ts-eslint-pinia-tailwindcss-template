<template>
  <view class="flex flex-col items-center p-4">
    <view class="mb-6">
      <text class="text-4xl font-bold text-gray-800">{{ counter.count }}</text>
    </view>

    <view class="flex space-x-3">
      <view
        class="bg-red-500 hover:bg-red-600 text-white font-bold py-2 px-4 rounded-md transition-colors shadow-sm" 
        @tap="onSubtract"
      >
        -
      </view>

      <view
        class="bg-blue-500 hover:bg-blue-600 text-white font-bold py-2 px-4 rounded-md transition-colors shadow-sm" 
        @tap="onAdd"
      >
        +
      </view>

      <view
        class="bg-gray-500 hover:bg-gray-600 text-white font-bold py-2 px-4 rounded-md transition-colors shadow-sm" 
        @tap="onReset"
      >
        Reset
      </view>
    </view>

    <view v-if="counter.count !== 0" class="mt-4 p-2 bg-gray-100 rounded text-sm text-gray-600">
      <text>Counter has been changed {{ counter.count > 0 ? counter.count : Math.abs(counter.count) }} time{{ counter.count !== 1 && counter.count !== -1 ? 's' : '' }}</text>
    </view>
  </view>
</template>

<script>
import { useCounterStore } from '../stores/counter'

export default {
  setup() {
    const counter = useCounterStore()

    const onAdd = () => {
      counter.increment()
    }

    const onSubtract = () => {
      counter.decrement()
    }

    const onReset = () => {
      counter.reset()
    }

    return {
      counter,
      onAdd,
      onSubtract,
      onReset
    }
  }
}
</script>

<style>
/* All styles now handled by Tailwind classes */
</style>
