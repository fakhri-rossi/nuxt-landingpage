<template>
  <PageContainer>
    <h1 class="text-2xl font-bold">About Me!</h1>
  </PageContainer>
</template>

<script lang="ts" setup>
  definePageMeta({
    layout: 'page'
  });

  useSeoMeta({
    title: 'About'
  })

  const leadingsText = computed(() => [
  {
    text: 'LANDING PAGE',
    startColor: '#00DC82',
    endColor: '#80EEC0',
    delay: 0,
  },
  {
    text: 'NUXT 3',
    startColor: '#00DC82',
    endColor: '#37E6BC',
    delay: 2,
  },
  {
    text: 'TAILWIND',
    startColor: '#0EB8D5',
    endColor: '#A8F3FC',
    delay: 4,
  },
])
</script>