<script setup lang="ts">
import { icons } from './icons'

const props = defineProps<{
  name?: keyof typeof icons
  text?: string
  size?: 'sm' | 'md' | 'lg'
  background?: boolean
  ariaLabel?: string
}>()

const icon = props.name ? icons[props.name] : null

const svgSizes = {
  sm: 'w-4 h-4',
  md: 'w-6 h-6',
  lg: 'w-8 h-8',
}

const textSizes = {
  sm: 'w-8 h-8 text-xl p-6',
  md: 'w-10 h-10 text-2xl p-8',
  lg: 'w-12 h-12 text-4xl p-10',
}

const frameClasses = props.background
  ? 'rounded-lg flex items-center justify-center border border-[var(--color-border-default)]'
  : ''
</script>

<template>
  <component
    :is="icon"
    v-if="icon"
    :class="[svgSizes[size ?? 'md'], frameClasses]"
    :role="ariaLabel ? 'img' : undefined"
    :aria-label="ariaLabel"
    :aria-hidden="!ariaLabel"
  />
  <span
    v-else-if="text"
    :class="[textSizes[size ?? 'md'], frameClasses]"
    :role="ariaLabel ? 'img' : undefined"
    :aria-label="ariaLabel"
    :aria-hidden="!ariaLabel"
  >
    {{ text }}
  </span>
</template>
