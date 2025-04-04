<script setup lang="ts">
useHead({
  title: 'Pronosticon - Resultados de Lotería',
  meta: [
    { 
      name: 'description', 
      content: 'Resultados de lotería en tiempo real, pronósticos y estadísticas. Florida Lottery, Lotería Nacional, Gordito y más.' 
    },
    {
      name: 'keywords',
      content: 'lotería, resultados, pronósticos, Florida Lottery, Lotería Nacional, Gordito, Tres Monazos'
    },
    {
      property: 'og:title',
      content: 'Pronosticon - Tu Portal de Lotería'
    },
    {
      property: 'og:description',
      content: 'Descubre los últimos resultados y pronósticos de tus loterías favoritas.'
    }
  ],
  link: [
    { rel: 'icon', type: 'image/png', href: '/favicon.png' }
  ],
})
</script>

<template>
    <div class="bg-gray-50 dark:bg-gray-900">
        <SectionsHomeHeroSection/>
        <SectionsHomeLatestPodcast/>
        <SectionsAboutPodux/>
        <SectionsWhyUs/>
        <SectionsCallToAction/>
    </div>
</template>

<style>
html {
    scroll-behavior: smooth;
}
</style>