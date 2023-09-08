<script setup>
import ChevronDownIcon from '@/components/icons/IconChevronDown.vue'
import { ref } from 'vue'
const { question, answer } = defineProps(['question', 'answer'])

const CouroselOpened = ref(false)

function toggleRotation() {
  CouroselOpened.value = !CouroselOpened.value
}
</script>

<template>
  <div class="border-b-[0.3px] border-[#ffffff89] pb-4">
    <div
      class="flex cursor-pointer items-center justify-between py-3 lg:py-4"
      @click="toggleRotation"
    >
      <span class="text-2xl font-semibold text-white lg:text-3xl">{{ question }}</span>

      <span :class="{ 'rotate-90-open': CouroselOpened, 'rotate-90-close': !CouroselOpened }">
        <ChevronDownIcon />
      </span>
    </div>

    <p
      v-if="CouroselOpened"
      class="rounded-2xl bg-[#fc5e13de] px-6 py-4 font-urbanist text-xl font-bold text-[#121139] lg:py-6 lg:text-2xl"
    >
      {{ answer }}
    </p>
  </div>
</template>

<style scoped>
.rotate-90-open {
  transform: rotate(-90deg);
  transition: transform 0.3s ease;
}
.rotate-90-close {
  transform: rotate(0deg);
  transition: transform 0.3s ease;
}
</style>
