<script setup>

defineProps({
  data: Object,
})

</script>

<template>
  <footer class="site-footer">
    <div class="inner">
      <div class="footer-left">
        <p>© 2025 <strong>{{ data.company.name }}</strong>. All rights reserved.</p>
      </div>
      <div class="footer-right">
        <p><strong>Address:</strong> {{ data.footer.address }}</p>
        <p><strong>Phone:</strong> {{ data.footer.phone }}</p>
      </div>
    </div>
  </footer>
</template>

<style scoped>

</style>
