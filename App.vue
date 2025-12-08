<script setup>
import { onMounted, ref } from 'vue'
import api from '@/services/api'

import HelloWorld from './components/HelloWorld.vue'
import Head from './components/Head.vue'
import Footer from "./components/Footer.vue";

const dataReference = ref(null)

onMounted(async () => {
  await api.get('/data').then(response => {
    console.log("API Response", response.data)

    dataReference.value = response.data
  }).catch(error => {
    // Só entra aqui se quiser tratar algo específico além do toast global
    if (error.response?.status === 404) {
      // ex: redirecionar para lista
      // navigateTo('/produtos')
    }
  })

  document.querySelectorAll(".fade-in").forEach((el, idx) => {
    el.style.animationDelay = `${0.12 * idx}s`;
  })
})
</script>

<template>
<!doctype html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <div v-if="dataReference">
      <title>{{ dataReference.company.name }} — Home</title>
    </div>
    <div v-else>
      <title>Home</title>
    </div>
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700&family=Open+Sans:ital,wght@0,400;0,600;1,400&display=swap" rel="stylesheet">
  </head>
  <body>
  <div v-if="dataReference">
    <Head :data="dataReference" />

    <!-- <RouterLink :to="{ name: '' }">← Voltar</RouterLink> -->
    <RouterView :data="dataReference" />

    <Footer :data="dataReference"/>
  </div>
  <div v-else>Loading…</div>
  </body>
</html>
</template>

<style scoped>

</style>
