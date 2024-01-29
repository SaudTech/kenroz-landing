<script setup>
import { defineProps } from "vue";

const props = defineProps({
  question: String,
  answer: String,
  isExpanded: Boolean
});

const emit = defineEmits(['toggle']);
</script>

<template>
  <div class="w-full bg-white p-2 rounded-md">
    <div
      @click="emit('toggle')"
      class="cursor-pointer font-bold flex justify-between items-center"
    >
      {{ props.question }}
      <span class="text-2xl select-none">{{ props.isExpanded ? '-' : '+' }}</span>
    </div>
    <div v-if="props.isExpanded" class="animation">
      {{ props.answer }}
    </div>
  </div>
</template>