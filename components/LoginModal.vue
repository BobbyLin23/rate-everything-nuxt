<script setup lang="ts">
defineProps<{
  visible: boolean;
}>()
</script>

<template>
  <UModal :model-value="visible">
    <UCard :ui="{ divide: 'divide-y divide-gray-100 dark:divide-gray-800' }">
      <template #header>
        <div class="flex items-center justify-between">
          <span class="font-semibold">Sign In</span>
          <Icon name="carbon:close" class="w-6 h-6 cursor-pointer" @click="$emit('close')" />
        </div>
      </template>
      <form class="space-y-4">
        <UFormGroup label="Email" required>
          <UInput type="email" icon="i-heroicons-envelope" />
        </UFormGroup>
        <UFormGroup label="Password" required>
          <UInput type="password" icon="i-heroicons-lock-closed" />
        </UFormGroup>
        <UButton block color="primary">Sign In</UButton>
      </form>
      <template #footer>
        <div class="flex items-center justify-between">
          <UButton color="gray" variant="link">Forget Password</UButton>
          <UButton color="gray" variant="link">New User?</UButton>
        </div>
        <UButton block color="gray" icon="i-carbon-github" class="mt-2">Github</UButton>
      </template>
    </UCard>
  </UModal>
</template>

<style scoped></style>
