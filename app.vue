<template>
  <NuxtLayout>
    <NuxtPage />
    <NuxtRouteAnnouncer />
  </NuxtLayout>
</template>

<script setup>
import { useHead } from '#imports'

useHead({
  title: 'Calculadora de Eficiência Energética - Calcule o Consumo de Energia do seu PC',
  meta: [
    { name: 'description', content: 'Utilize nossa calculadora de eficiência energética para calcular o consumo do seu computador, obter dicas de economia de energia e contribuir para a sustentabilidade.' },
    { name: 'keywords', content: 'eficiência energética, consumo de energia, calculadora de energia, computador, PC, economia de energia, sustentabilidade' },
    { name: 'robots', content: 'index, follow' },
    { property: 'og:title', content: 'Calculadora de Eficiência Energética - Calcule o Consumo de Energia do seu PC' },
    { property: 'og:description', content: 'Descubra como otimizar o consumo de energia do seu computador e economizar com dicas práticas para um uso mais sustentável.' },
    { property: 'og:type', content: 'website' },
    { property: 'og:url', content: 'https://seusite.com/energy-efficiency-calculator/' }
  ],
  link: [
    { rel: 'icon', type: 'image/x-icon', href: '/favicon.ico' }
  ]
})
</script>
