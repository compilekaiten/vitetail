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
    <div class="flex justify-center gap-3">
      <i-logos:vitejs class="h-12 w-12" />
      <i-logos:tailwindcss-icon class="h-12 w-12" />
      <i-ion:flower-sharp class="h-12 w-12 text-yellow-400" />
    </div>
    <div class="mockup-code mt-5 bg-inherit">
      <pre data-prefix="$"><code>ViteTail</code></pre>
      <pre data-prefix=">" class="text-warning"><code class="text-warning">Vite + TailwindCSS + DaisyUI</code></pre>
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
