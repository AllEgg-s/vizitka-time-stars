<template>
  <nav class="breadcrumbs" aria-label="Хлебные крошки">
    <NuxtLink to="/" class="breadcrumbs__link">Главная</NuxtLink>
    <span v-for="(item, i) in items" :key="i" class="breadcrumbs__item">
      <span class="breadcrumbs__sep">/</span>
      <NuxtLink v-if="item.to" :to="item.to" class="breadcrumbs__link">{{ item.title }}</NuxtLink>
      <span v-else class="breadcrumbs__current">{{ item.title }}</span>
    </span>
  </nav>
</template>

<script setup lang="ts">
interface BreadcrumbItem {
  title: string
  to?: string
}
defineProps<{
  items: BreadcrumbItem[]
}>()
</script>

<style scoped>
.breadcrumbs {
  font-size: 0.9rem;
  color: var(--color-text-muted);
  margin-bottom: 1rem;
}
.breadcrumbs__link {
  text-decoration: none;
  color: var(--color-text-muted);
}
.breadcrumbs__link:hover {
  color: var(--color-text);
}
.breadcrumbs__sep {
  margin: 0 0.5rem;
}
.breadcrumbs__current {
  color: var(--color-text);
}
</style>
