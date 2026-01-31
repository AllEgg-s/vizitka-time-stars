<template>
  <div class="page kontakty-page">
    <div class="container">
      <Breadcrumbs :items="[{ title: 'Главная', to: '/' }, { title: 'Контакты' }]" />
      <h1 class="page__title">Контакты</h1>
      <div class="kontakty__content">
        <p><strong>Адрес:</strong> Москва, Митино, Айс Арена ЦХМ</p>
        <p><strong>Телефон:</strong> <a :href="`tel:${phoneRaw}`">{{ phone }}</a></p>
        <p><strong>E-mail:</strong> <a :href="`mailto:${email}`">{{ email }}</a></p>
      </div>
      <div class="kontakty__map">
        <div class="media-placeholder">Тут может быть карта</div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
const phone = '+7 (495) 323-88-87'
const phoneRaw = '74953238887'
const email = 'info@hockey-chm.ru'
</script>

<style scoped>
.page {
  padding: 2rem 0 3rem;
}
.page__title {
  font-size: 2rem;
  margin: 0 0 1.5rem;
}
.kontakty__content p {
  margin: 0 0 0.75rem;
  line-height: 1.5;
}
.kontakty__content a {
  color: var(--color-accent);
  text-decoration: none;
}
.kontakty__content a:hover {
  text-decoration: underline;
}
.kontakty__map {
  margin-top: 2rem;
  aspect-ratio: 16/9;
  max-width: 800px;
  background: var(--color-surface);
  border: 1px solid var(--color-border);
  border-radius: var(--radius);
  display: flex;
  align-items: center;
  justify-content: center;
  color: var(--color-text-muted);
  font-size: 0.95rem;
}
</style>
