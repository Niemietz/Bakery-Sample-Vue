<script setup>
import { navigateTo } from '@/router/navigation.ts'
import { onMounted } from 'vue'
import Swal from 'sweetalert2'

defineProps({
  data: Object,
  submitted: Boolean,
})

onMounted(async () => {

})
</script>

<template>
  <main class="container fade-in contact-page">
    <h2>Contact Us</h2>
    <p><strong>Phone:</strong> {{ data.footer.phone }}</p>
    <p><strong>Address:</strong> {{ data.footer.address }}</p>

    <div v-if="submitted">
      <div class="success">✅ Thanks! Your message has been received.</div>
    </div>
    <div v-else>
      <form action="/contact" method="POST" class="contact-form">
        <label>Name</label>
        <input name="name" type="text" required>
        <label>Email</label>
        <input name="email" type="email" required>
        <label>Message</label>
        <textarea name="message" required></textarea>
        <button class="primary-btn" type="submit">Send Message</button>
      </form>
    </div>
  </main>
</template>

<style scoped>

</style>