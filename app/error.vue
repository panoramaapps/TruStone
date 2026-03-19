<template>
  <div class="min-h-screen flex items-center justify-center p-8">
    <div class="text-center">
      <h1 class="text-2xl font-bold text-slate-900 dark:text-slate-100">
        {{ error?.statusCode ?? 500 }}
      </h1>
      <p class="mt-2 text-slate-600 dark:text-slate-400">
        {{ error?.message ?? 'Something went wrong' }}
      </p>
      <UButton class="mt-6" @click="handleBack">
        Go back
      </UButton>
    </div>
  </div>
</template>

<script setup lang="ts">
const error = useError()

function handleBack() {
  clearError({ redirect: '/' })
}
</script>
