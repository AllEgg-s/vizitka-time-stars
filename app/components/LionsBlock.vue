<template>
  <section class="lions section">
    <div class="container lions__inner">
      <div class="lions__title-wrap">
        <h2 class="lions__title">Львы ЦХМ приглашают на просмотр!</h2>
      </div>
      <div class="lions__media">
        <div class="media-placeholder">Тут может быть картинка</div>
      </div>
      <div class="lions__content">
        <p class="lions__text">Идет набор игроков 2017 г.р.</p>
      </div>
      <div class="lions__action">
        <NuxtLink to="/abonementy" class="btn">Подробнее</NuxtLink>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
</script>

<style scoped>
.section {
  padding: 3rem 0;
}
.lions__inner {
  display: grid;
  grid-template-columns: 1fr auto 1fr;
  gap: 2rem;
  align-items: center;
}
.lions__title-wrap {
  text-align: right;
  min-width: 0;
}
.lions__title {
  font-size: 1.75rem;
  margin: 0;
}
.lions__media {
  width: 140px;
  aspect-ratio: 1;
  background: var(--color-surface);
  border: 1px solid var(--color-border);
  border-radius: var(--radius);
  display: flex;
  align-items: center;
  justify-content: center;
  color: var(--color-text-muted);
  font-size: 0.75rem;
  text-align: center;
  padding: 0.5rem;
}
.lions__content {
  min-width: 0;
  text-align: left;
}
.lions__text {
  margin: 0;
  font-size: 1rem;
  line-height: 1.5;
  color: var(--color-text-muted);
}
.lions__action {
  grid-column: 1 / -1;
  display: flex;
  justify-content: center;
  margin-top: 0.5rem;
}
@media (max-width: 768px) {
  .lions__inner {
    grid-template-columns: 1fr;
  }
  .lions__title-wrap {
    text-align: center;
    order: 1;
  }
  .lions__media {
    margin: 0 auto;
    order: 2;
  }
  .lions__content {
    text-align: center;
    order: 3;
  }
  .lions__action {
    order: 4;
  }
}
</style>
