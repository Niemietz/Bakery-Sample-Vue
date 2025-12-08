<script setup>
import { navigateTo } from '@/router/navigation.ts'
import { onMounted } from 'vue'
import Swal from 'sweetalert2'

onMounted(async () => {

})
</script>

<template>
  <main class="container fade-in about-page">
    <h2>About Us</h2>
    <p>Founded in 2010, our bakery blends traditional techniques with creative flavors. We bake small batches daily and love serving the local community delicious baked goods made from the finest ingredients.</p>

    <div class="about-grid">
      <div class="about-image" style="background-image: url('https://images.unsplash.com/photo-1517248135467-4c7edcad34c4?auto=format&fit=crop&w=1200&q=80')"></div>
      <div class="about-content">
        <h3>Our Mission</h3>
        <p>To share handcrafted baked goods that bring comfort and delight — made with honesty and passion.</p>
        <h3>Our Team</h3>
        <p>A small, talented team of bakers and pastry chefs with years of experience.</p>
      </div>
    </div>
  </main>
</template>

<style scoped>

</style>