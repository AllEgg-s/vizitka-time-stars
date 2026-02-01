<template>
  <section class="hero">
    <div class="hero__inner container">
      <h1 class="hero__title">Стань частью нашей команды!</h1>
    </div>
  </section>
</template>

<script setup lang="ts">
</script>

<style scoped>
.hero {
  padding: 4rem 0;
  background: linear-gradient(180deg, var(--color-surface) 0%, var(--color-bg) 100%);
  text-align: center;
}
.hero__inner {
  max-width: 600px;
}
.hero__title {
  font-size: 2.5rem;
  margin: 0;
  line-height: 1.2;
}
@media (max-width: 600px) {
  .hero__title {
    font-size: 1.75rem;
  }
}
</style>
