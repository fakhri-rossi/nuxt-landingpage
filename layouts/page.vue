<template>
  <div class="dark:bg-gray-950 dark:text-gray-100 light:bg-gray-200 light:text-gray-800 min-h-screen flex flex-col">
    <!-- bg-gray-500/50 artinya gray 50 oppacity 50 -->
    <header class="h-[38px] sticky w-full z-30 top-0 border-b flex backdrop-blur-lg dark:border-gray-500/50 dark:bg-gray-950/50 light:border-gray-800/50 light:bg-gray-50/50"> 
      <PageContainer class="flex flex-1 items-center justify-between">
        
        <NuxtLink to="/" class="font-bold text-lg">
          Landing Page
        </NuxtLink>

        <ul class="flex justify-evenly items-center gap-4">
          <li v-for="(menu, i) in menus" :key="i">
            <NuxtLink :to="menu.to" class="hover:text-primary">{{ menu.label }}</NuxtLink>
          </li>

          <li>
            <ToggleColorMode />
          </li>
        </ul>

      </PageContainer>
    </header>
    
    <main class="flex-1 flex">
      <slot />
    </main>

    <footer class="border-t border-gray-500/50 min-h-[38px] flex">
      <PageContainer class="flex flex-1 flex-col py-4">
        
        <NuxtLink to="https://www.github.com/fakhri-rossi" target="_blank">
          <div class="flex items-center gap-2 hover:text-green-500">
            <UIcon name="mdi:github" class="text-xl" />
            fakhri-rossi
          </div>
        </NuxtLink>

        <NuxtLink to="https://www.instagram.com/fkhr_rossi/" target="_blank">
          <div class="flex items-center gap-2 hover:text-green-500">
            <UIcon name="mdi:instagram" class="text-xl" />
            fkhr_rossi
          </div>
        </NuxtLink>

        <div class="flex mt-2">
          <span class="text-sm">&copy; 2024</span>
        </div>

      </PageContainer>
    </footer>

  </div>
</template>

<script lang="ts" setup>
  const menus = ref([
    { label: 'Home', to: '/' },
    { label: 'About', to: '/about' },
    { label: 'Contact', to: '/contact' },
  ])
</script>

<style>

</style>