<template>
  <button 
    :class="buttonClass" 
    @click="handleClick">
    <slot></slot>
  </button>
</template>

<script setup>
import { defineProps, defineEmits, computed} from 'vue';

const props = defineProps({
  type: {
    type: String,
    default: 'button',
  },
  color: {
    type: String,
    default: 'blue',
  },
  size: {
    type: String,
    default: 'medium',
  },
});

const emit = defineEmits(['click']);

const handleClick = (event) => {
  emit('click', event);
};

const buttonClass = computed(() => {
  const baseClasses = 'rounded-full px-4 py-2 font-medium focus:outline-none';
  const colorClasses = {
    cyan: 'bg-cyan text-white hover:bg-opacity-50',
  };
  const sizeClasses = {
    small: 'text-xs',
    medium: 'text-sm',
  };

  return `${baseClasses} ${colorClasses[props.color] || colorClasses.blue} ${sizeClasses[props.size] || sizeClasses.medium}`;
});
</script>

<style scoped>
</style>