<script setup lang="ts">
const props = defineProps<{ name: string }>()
const router = useRouter()
const user = useUserStore()

watchEffect(() => {
  user.setNewName(props.name)
})
</script>

<template>
  <div class="container mx-auto flex justify-center">
    Hello {{ props.name }}

    <button class="btn btn-square btn-error" @click="router.back()">
      Back
    </button>
  </div>
</template>
