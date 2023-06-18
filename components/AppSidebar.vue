<script setup lang="ts">
import useLoginModal from '~/composables/useLoginModal'

const loginModal = useLoginModal()

const colorMode = useColorMode()

function openLoginModal () {
  loginModal.value = true
}

const isDark = computed({
  get () {
    return colorMode.value === 'dark'
  },
  set () {
    colorMode.preference = colorMode.value === 'dark' ? 'light' : 'dark'
  }
})
</script>

<template>
  <aside
    class="w-[200px] h-[calc(100vh-64px)] xl:w-[300px] flex flex-col justify-between"
  >
    <div
      class="w-full p-4 pl-8 xl:pl-12 flex flex-col gap-y-4 text-neutral-700 dark:text-neutral-500"
    >
      <div
        class="w-full rounded-xl py-2 px-2 lg:px-4 flex items-center gap-2 hover:bg-neutral-100 dark:hover:bg-neutral-800 cursor-pointer"
      >
        <Icon name="carbon:earth-southeast-asia-filled" class="w-6 h-6" />
        <span>Explore</span>
      </div>
      <div
        class="w-full rounded-xl py-2 px-2 lg:px-4 flex items-center gap-2 hover:bg-neutral-100 dark:hover:bg-neutral-800 cursor-pointer"
      >
        <Icon name="carbon:add-alt" class="w-6 h-6" />
        <span>Rate</span>
      </div>
      <div
        v-if="false"
        class="w-full rounded-xl py-2 px-2 lg:px-4 flex items-center gap-2 hover:bg-neutral-100 dark:hover:bg-neutral-800 cursor-pointer"
      >
        <Icon name="carbon:user-avatar-filled-alt" class="w-6 h-6" />
        <span>Profile</span>
      </div>
      <UButton
        v-else
        variant="solid"
        size="lg"
        block
        @click="openLoginModal"
        >
        Sign In
      </UButton>
    </div>
    <div class="w-full p-4 flex flex-col gap-y-4 text-xs text-neutral-400">
      <!-- <Icon
        name="carbon:sun"
        class="w-6 h-6 cursor-pointer hover:text-neutral-800 dark:hover:text-neutral-500"
      /> -->
      <ClientOnly>
        <UButton
          :icon="isDark ? 'i-heroicons-moon-20-solid' : 'i-heroicons-sun-20-solid'"
          color="gray"
          variant="ghost"
          aria-label="Theme"
          class="w-8 h-8"
          @click="isDark = !isDark"
        />

        <template #fallback>
          <div class="w-8 h-8" />
        </template>
      </ClientOnly>
      <span>About</span>
      <span>Source Code</span>
    </div>
  </aside>
</template>

<style scoped></style>
