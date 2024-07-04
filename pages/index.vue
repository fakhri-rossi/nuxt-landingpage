<template>
  <div class="flex flex-col flex-1">
    <section class="flex flex-col justify-center items-center min-h-[calc(100vh)]">
      <h1 class="text-center mt-4">
        <span
          v-for="(item, i) in leadingsText"
          :key="i"
          :style="`--content: '${item.text}'; --start-color: ${
            item.startColor
          }; --end-color: ${item.endColor}; --animation-name: anim-fg-${
            i + 1
          }`"
          class="animated-text-bg drop-shadow-xl text-4xl sm:text-8xl md:text-8xl lg:text-8xl 2xl:text-8xl block font-black uppercase"
          >
          <span class="animated-text-fg">{{ item.text }}</span>
        </span>
      </h1>
  
      <div class="max-w-[500px] mt-4">
        <p class="text-center dark:text-gray-400 light:text-gray-700">
          Lorem, ipsum dolor sit amet consectetur adipisicing elit. Lorem ipsum dolor sit amet consectetur adipisicing elit. Quo esse id itaque error quae velit mollitia!
        </p>
      </div>
  
  
      <div class="flex justify-center gap-4 mt-4">
         <UButton label="Get Started"/>
         <UButton color="white" label="Read More" />
      </div>
    </section>

    <section class="center min-h-[calc(100vh-78px)] flex justify-center items-center dark:bg-gray-900">
      <h1 class="text-white font-bold text-2xl text-center">Ini Section</h1>
    </section>
  </div>
</template>

<script lang="ts" setup>
  definePageMeta({
    layout: 'page'
  })

  useSeoMeta({
    title: 'Home'
  })

  const leadingsText = computed(() => [
  {
    text: 'LANDING PAGE',
    startColor: '#00DC82',
    endColor: '#0EB8D5',
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

<style lang="scss" >
:root {
  --padding: 0.05em;
}

@keyframes anim-fg-1 {
  0%,
  16.667%,
  100% {
    opacity: 1;
  }
  33.333%,
  83.333% {
    opacity: 0;
  }
}
@keyframes anim-fg-2 {
  0%,
  16.667%,
  66.667%,
  100% {
    opacity: 0;
  }
  33.333%,
  50% {
    opacity: 1;
  }
}
@keyframes anim-fg-3 {
  0%,
  50%,
  100% {
    opacity: 0;
  }
  66.667%,
  83.333% {
    opacity: 1;
  }
}
.animated-text-bg {
  position: relative;
  display: block;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
  content: var(--content);
  display: block;
  width: 100%;
  color: theme('colors.slate.800');
  top: 0;
  bottom: 0;
  left: 0;
  z-index: 0;
  padding-left: var(--padding);
  padding-right: var(--padding);
  &:before {
    content: var(--content);
    position: absolute;
    display: block;
    width: 100%;
    color: theme('colors.slate.800');
    top: 0;
    bottom: 0;
    left: 0;
    z-index: 0;
    padding-left: var(--padding);
    padding-right: var(--padding);
  }
}
.animated-text-fg {
  background-clip: text;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  padding-left: var(--padding);
  padding-right: var(--padding);
  background-image: linear-gradient(
    90deg,
    var(--start-color),
    var(--end-color)
  );
  position: relative;
  opacity: 0;
  z-index: 1;
  animation: var(--animation-name) 8s infinite;
}
html.dark {
  .animated-text-bg {
    color: theme('colors.gray.100');
    &:before {
      color: theme('colors.gray.100');
    }
  }
}
</style>