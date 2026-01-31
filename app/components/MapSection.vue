<template>
  <section class="map-section section">
    <div class="container">
      <h2 class="section-title">Где мы находимся?</h2>
      <div class="map-section__placeholder">
        Тут может быть карта
      </div>
      <p class="map-section__address">Москва, Митино, Айс Арена ЦХМ</p>
    </div>
  </section>
</template>

<script setup lang="ts">
</script>

<style scoped>
.map-section__placeholder {
  aspect-ratio: 16/9;
  background: var(--color-surface);
  border: 1px solid var(--color-border);
  border-radius: var(--radius);
  display: flex;
  align-items: center;
  justify-content: center;
  color: var(--color-text-muted);
  font-size: 1rem;
  margin-bottom: 1rem;
}
.map-section__address {
  text-align: center;
  margin: 0;
  color: var(--color-text-muted);
}
</style>
