<script setup lang="ts">
const user = useUserStore()
const name = $ref(user.savedName)

const router = useRouter()
const go = () => {
  if (name)
    router.push(`/hi/${encodeURIComponent(name)}`)
}
</script>

<template>
  <div class="container mx-auto grid justify-center pt-10">
    <div class="grid grid-rows-1 justify-center">
      <img src="/pwa-512x512.png" alt="ViteTail Logo" width="100" heigh="100">
    </div>

    <div class="flex flex-row justify-between pt-5">
      <i-logos:vitejs class="h-12 w-12" />
      <i-logos:tailwindcss-icon class="h-14 w-14" />
      <i-fxemoji:blossom class="h-12 w-12" />
    </div>

    <div class="mockup-code mt-5 bg-base-200">
      <pre data-prefix="$"><code>ViteTail</code></pre>
      <pre data-prefix=">" class="text-error"><code class="text-error">Vite + TailwindCSS + DaisyUI</code></pre>
      <pre data-prefix=">" class="text-success"><code>Inspired by Vitesse</code></pre>
    </div>
  </div>

  <div class="container mx-auto grid justify-center py-5">
    <input id="input" v-model="name" type="text" placeholder="What's your name?" class="input input-bordered w-full mb-5 focus:input-info" autocomplete="off">
    <button
      id="go"
      class="btn btn-wide btn-success" :disabled="!name"
      @click="go"
    >
      GO
    </button>
  </div>
</template>

<route lang="yaml">
meta:
  layout: home
</route>
