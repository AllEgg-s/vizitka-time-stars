<template>
  <section class="hero">
    <div class="hero__inner container">
      <h1 class="hero__title">Стань частью команды!</h1>
      <LeadForm />
      <p class="hero__disclaimer">Заполняя и отправляя форму, Вы даете Согласие на обработку персональных данных</p>
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
  margin: 0 0 1.5rem;
  line-height: 1.2;
}
.hero__disclaimer {
  margin: 1rem 0 0;
  font-size: 0.8rem;
  color: var(--color-text-muted);
}
@media (max-width: 600px) {
  .hero__title {
    font-size: 1.75rem;
  }
}
</style>
