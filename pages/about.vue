<script setup lang="ts">
</script>

<template>
  <div>
    <h1>Nuxt Vite PWA</h1>
    <PwaTransparentImage image="pwa-192x192.png" alt="PWA Icon" />
    {{ $pwaIcons?.favicon['favicon.ico']?.asImage }}
    {{ $pwaIcons?.transparent['pwa-192x192.png']?.asImage }}
    {{ $pwaIcons?.transparent['pwa-192x192.png']?.url }}
    <ClientOnly>
      PWA Installed: {{ $pwa?.isPWAInstalled }}
    </ClientOnly>
    <NuxtLink to="/">
      Home 1
    </NuxtLink>
  </div>
</template>
