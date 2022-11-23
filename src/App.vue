<script setup lang="ts">
import { useSeoMeta } from '@vueuse/head'
// https://github.com/vueuse/head
// you can use this to manipulate the document head in any components,
// they will be rendered correctly in the html results with vite-ssg
useHead({
  title: 'ViteTail',
  meta: [
    {
      name: 'description',
      content: 'Vite Stater Template. Now with TailwindCSS!',
    },
    {
      name: 'theme-color',
      content: '#141824',
    },
  ],
  link: [
    {
      rel: 'icon',
      type: 'image/svg+xml',
      href: '/favicon.ico',
    },
  ],
})

useSeoMeta({
  description: 'ViteTail - Vite Starter Template',
  ogDescription: 'ViteTail - A Vite/Vue3/TailwindCSS SSG starter template.',
  ogTitle: 'ViteTail',
})
</script>

<template>
  <RouterView />
</template>
