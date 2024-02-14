<script setup lang="ts">
const pwaIcons = useNuxtApp().$pwaIcons!
console.log(pwaIcons.appleSplashScreen['apple-splash-landscape-dark-2048x1536.png']?.url)
const { icon: icon64 } = useTransparentPwaIcon({
  image: 'pwa-64x64.png',
  alt: 'PWA Icon'
})
const { icon: icon192 } = useTransparentPwaIcon('pwa-192x192.png')
</script>

<template>
  <div>
    <h1>Nuxt Vite PWA</h1>
    <PwaTransparentImage image="pwa-64x64.png" alt="PWA Icon" />
    <img
      v-if="icon64"
      v-bind="icon64"
    >
    <img
      v-if="$pwaIcons?.transparent"
      v-bind="$pwaIcons.transparent['pwa-64x64.png']?.asImage"
      alt="PWA Icon"
    >
    <img
      v-if="$pwaIcons?.favicon"
      v-bind="$pwaIcons.favicon['favicon.ico']?.asImage"
      alt="PWA Icon"
    >
    <ClientOnly>
      PWA Installed: {{ $pwa?.isPWAInstalled }}
    </ClientOnly>
    <NuxtLink to="/about">
      About
    </NuxtLink>
  </div>
</template>
