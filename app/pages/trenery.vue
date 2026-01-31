<template>
  <div class="page trenery-page">
    <div class="container">
      <Breadcrumbs :items="[{ title: 'Главная', to: '/' }, { title: 'Тренеры' }]" />
      <h1 class="page__title">Тренеры</h1>
      <p class="trenery__stub">Тут будут тренера</p>
    </div>
  </div>
</template>

<script setup lang="ts">
definePageMeta({
  layout: 'default'
})
</script>

<style scoped>
.page {
  padding: 2rem 0 3rem;
}
.page__title {
  font-size: 2rem;
  margin: 0 0 1rem;
}
.trenery__stub {
  margin: 0;
  color: var(--color-text-muted);
  font-size: 1.1rem;
}
</style>
