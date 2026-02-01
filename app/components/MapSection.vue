<template>
  <section class="map-section section">
    <div class="container">
      <h2 class="section-title">Где мы находимся?</h2>
      <div class="map-section__map">
        <iframe
          src="https://yandex.ru/map-widget/v1/?ll=39.902303%2C57.583665&z=16&pt=39.902303%2C57.583665"
          width="100%"
          height="100%"
          allowfullscreen
          title="Карта"
          class="map-section__iframe"
        />
      </div>
      <p class="map-section__address">Дядьковская улица, 7, Ярославль, 150006</p>
    </div>
  </section>
</template>

<script setup lang="ts">
</script>

<style scoped>
.map-section__map {
  aspect-ratio: 16/9;
  border-radius: var(--radius);
  overflow: hidden;
  position: relative;
  margin-bottom: 1rem;
}
.map-section__iframe {
  position: absolute;
  inset: 0;
  border: 0;
  border-radius: inherit;
}
.map-section__address {
  text-align: center;
  margin: 0;
  color: var(--color-text-muted);
}
</style>
