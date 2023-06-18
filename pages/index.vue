<template>
  <section class="w-screen h-screen">
    <AppHeader />
    <main class="flex">
      <AppSidebar />
      <ExploreContent />
    </main>
    <LoginModal :visible="loginModal" @close="loginModal = false" />
  </section>
</template>

<script setup lang="ts">
import useLoginModal from '~/composables/useLoginModal'

const loginModal = useLoginModal()
</script>

<style scoped>

</style>
