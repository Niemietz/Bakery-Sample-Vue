<script setup>
import { navigateTo } from '@/router/navigation.ts'
import { onMounted } from 'vue'
import Swal from 'sweetalert2'

defineProps({
  data: Object,
})

onMounted(async () => {

})
</script>

<template>
    <main>
      <section class="hero" :style="{ backgroundImage: `url(${data.hero.image})` }">
        <div class="hero-overlay">
          <h1 class="hero-headline">{{ data.hero.title }}</h1>
          <p class="hero-cta"><a class="primary-btn" href="#order">{{ data.hero.ctaText }}</a></p>
        </div>
      </section>

      <section class="why container fade-in">
        <h2>{{ data.sections.whyChooseUs.title }}</h2>
        <p class="lead">{{ data.sections.whyChooseUs.description }}</p>

        <div class="cards">
          <template v-for="cat in data.sections.whyChooseUs.features">
            <article class="card">
              <div class="card-image" :style="{ backgroundImage: `url(${cat.image})` }"></div>
              <h3>{{ cat.name }}</h3>
              <p>{{ cat.description }}</p>
              <p><a class="secondary-btn" href="#gallery">{{ cat.cta }}</a></p>
            </article>
          </template>
        </div>
      </section>

      <section id="gallery" class="gallery container fade-in">
        <h2>Gallery</h2>
        <div class="gallery-grid">
          <template v-for="img in data.sections.gallery">
            <div class="g-item" :style="{ backgroundImage: `url(${img})` }"></div>
          </template>
        </div>
      </section>

      <section class="visit container fade-in">
        <div class="visit-text">
          <h2>{{ data.footer.visitUs }}</h2>
          <p>{{ data.footer.visitUsDescription }}</p>
          <a class="primary-btn" href="/contact">{{ data.footer.visitUsCta_text }}</a>
        </div>
        <div class="visit-info">
          <h4>Visit</h4>
          <p><strong>Address:</strong> {{ data.footer.address }}</p>
          <p><strong>Phone:</strong> {{ data.footer.phone }}</p>
        </div>
      </section>

      <section class="bottom container fade-in">
        <div class="bottom-items">
          <template v-for="item in data.footer.bottom">
            <div class="bottom-item">
              <h4>{{ item.title }}</h4>
              <p>{{ item.description }}</p>
            </div>
          </template>
        </div>
      </section>
    </main>
</template>

<style scoped>

</style>