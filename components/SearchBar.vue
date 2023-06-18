<template>
  <UInput
    v-model="value"
    size="md"
    icon="i-humbleicons-search"
    placeholder="Search..."
    trailing
    class="w-[200px] md:w-[300px]"
  />
</template>

<script setup lang="ts">
const value = ref()
</script>

<style scoped></style>
