<script setup lang="ts">
import { themeChange } from 'theme-change'
import { tryOnMounted } from '@vueuse/core'

tryOnMounted(() => {
  themeChange(false)
})
</script>

<template>
  <div class="container flex flex-row justify-center">
    <RouterLink class="mx-2" to="/">
      <i-ri:home-line class="h-6 w-6 hover:text-green-500" />
    </RouterLink>

    <label id="theme-toggle" class="swap swap-flip mx-2">
      <input type="checkbox">
      <i-carbon-sun class="swap-off h-6 w-6 hover:text-yellow-500" data-set-theme="bumblebee" data-act-class="ACTIVECLASS" aria-label="theme-light-toggle" />

      <i-carbon-moon class="swap-on h-6 w-6 text-black hover:text-stone-500" data-set-theme="halloween" data-act-class="ACTIVECLASS" aria-label="theme-dark-toggle" />
    </label>

    <RouterLink class="mx-2" to="/about">
      <i-carbon-dicom-overlay class="h-6 w-6 hover:text-blue-500" />
    </RouterLink>

    <a class="mx-2" rel="noreferrer" href="https://github.com/antfu/vitesse" target="_blank" title="GitHub">
      <i-carbon-logo-github class="h-6 w-6 hover:text-purple-500" />
    </a>
  </div>
</template>
