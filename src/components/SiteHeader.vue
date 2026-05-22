<script setup lang="ts">
import { useRouter } from 'vue-router'
import content from '@/data/content-en.json'
import Icon from '@/components/Icon.vue'

const router = useRouter()
</script>

<template>
  <div class="flex flex-col">
    <button
      type="button"
      class="cursor-pointer rounded-2xl"
      @click="router.push({ name: 'home' })"
    >
      <h1>{{ content.title }}</h1>
    </button>
    <p class="pl-2">{{ content.tagline }}</p>
    <Icon name="eye" />
  </div>
</template>
