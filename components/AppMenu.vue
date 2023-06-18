<script setup lang="ts">
const items = [
  [
    {
      label: 'App'
    },
    {
      label: 'About'
    }
  ]
]
</script>

<template>
  <ul class="hidden xl:flex items-center gap-2 lg:gap-6 text-neutral-500">
    <li class="rounded-xl w-20 text-center py-2 hover:bg-neutral-100 dark:hover:bg-neutral-800 cursor-pointer">
      About
    </li>
    <li class="rounded-xl w-20 text-center py-2 hover:bg-neutral-100 dark:hover:bg-neutral-800 cursor-pointer">
      App
    </li>
  </ul>
  <div class="xl:hidden">
    <UDropdown :items="items" mode="hover" :popper="{ placement: 'bottom-start' }">
      <Icon name="carbon:menu" class="w-6 h-6 text-neutral-500 cursor-pointer" />
    </UDropdown>
  </div>
</template>

<style scoped>

</style>
