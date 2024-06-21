<template>
  <button 
    :class="buttonClass" 
    @click="handleClick">
    <slot></slot>
  </button>
</template>

<script setup>
import { computed} from 'vue';

const props = defineProps({
  type: {
    type: String,
    default: 'button',
  },
  color: {
    type: String,
    default: 'cyan',
  },
  size: {
    type: String,
    default: 'medium',
  },
  base: {
    type: String,
    default: 'roundedFull'
  }
}); 

const emit = defineEmits(['click']);

const handleClick = (event) => {
  emit('click', event);
};

const buttonClass = computed(() => {
  const baseClasses = {
    roundedFull: 'rounded-full px-4 py-2 font-medium focus:outline-none',
    roundedLg: 'rounded-lg px-4 py-2 font-medium focus:outline-none'
  };
  const colorClasses = {
    cyan: 'bg-cyan text-white hover:bg-opacity-50',
  };
  const sizeClasses = {
    small: 'text-xs',
    medium: 'text-sm',
  };

  return `${baseClasses[props.base] || baseClasses.roundedLg} ${colorClasses[props.color] || colorClasses.cyan} ${sizeClasses[props.size] || sizeClasses.medium}`;
});
</script>

<style scoped>
</style>