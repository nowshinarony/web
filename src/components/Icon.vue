<script setup lang="ts">
import { icons } from './icon'

const props = defineProps<{
  name: keyof typeof icons
}>()

const icon = icons[props.name]

</script>

<template>
 
 <component :is="icon" v-if="icon"/>

</template>
