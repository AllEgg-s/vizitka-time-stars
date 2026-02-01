<template>
  <div class="page abonementy-page">
    <div class="container">
      <Breadcrumbs :items="[{ title: 'Главная', to: '/' }, { title: 'Услуги' }]" />
      <h1 class="page__title">Услуги</h1>

      <div class="abonementy__grid">
        <article v-for="(item, i) in services" :key="i" class="abonementy-card">
          <div class="abonementy-card__media">
            <img :src="item.image" :alt="item.title" class="abonementy-card__img" />
          </div>
          <div class="abonementy-card__body">
            <h3 class="abonementy-card__type">{{ item.title }}</h3>
            <p class="abonementy-card__price">{{ item.price }}</p>
            <p v-if="item.desc" class="abonementy-card__period">{{ item.desc }}</p>
            <a href="https://vk.ru/market-125696800?screen=group" target="_blank" rel="noopener" class="btn">Купить</a>
          </div>
        </article>
      </div>

      <div class="abonementy__blocks">
        <div class="abonementy__block">
          <h3>Порядок использования абонемента</h3>
          <p>Приобретенный абонемент необходимо предъявлять в распечатанном или электронном виде тренеру или администратору по первому требованию при посещении тренировки. При отсутствии оплаченного абонемента или в случае истечения срока его действия тренер или администратор имеют право не допустить спортсмена до тренировки.</p>
        </div>
        <div class="abonementy__block">
          <h3>Возврат</h3>
          <p>Приобретенный абонемент необходимо предъявлять в распечатанном или электронном виде тренеру или администратору по первому требованию при посещении тренировки. При отсутствии оплаченного абонемента или в случае истечения срока его действия тренер или администратор имеют право не допустить спортсмена до тренировки.</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
definePageMeta({
  layout: 'default'
})

const shopImages = [
  '/shop/_twVtVDKeoN3qCQ8AlLgTWJR-9q5bV8mf8DJXZ5-yx9k-lA1iryii5q5wQ3G8mw54s95N9k_Kh5kNlEVH4j6AmAp.jpg',
  '/shop/b-eJHU_jVRGTsdGZKq3NtgV8-_0NnCJabsmuSioIBdmZMAi2b-oOIlaNI_Qp9q_TOuDjyg_PcTfHaRpu2EU36WcG.jpg',
  '/shop/glcWrrXS8JSFO4wHnFV80Y-7qClgdcrjfH0DZdsLyTJrsfG1UDFeDfGqlPNp4USitpUnsv1ojqEuvadcInoFl5kl.jpg',
  '/shop/Oeof_tqrSe_uVQUpMuytHbJeA4Dt3ffEHVqBqy3UtrxC3yx_aQEbZHI1EHLejSn234R46fBJdxCaw2w5D5CoXNTC.jpg',
  '/shop/OpuOGPC8HYB-Acy601CdHzBhNPncsOazsNvB7jx0h565jFN2LdV2OuWcQ0N6iN9qCKrNjTdta3LNAQG2S73QgmNV.jpg',
  '/shop/ycpRUs57C3dTwqqEVs1JnZ6NHLMIAXISRWcORSL4zcxfqRw4ExBUuYAlICbJ3gXIcvlTw-Vv6gfY0liqQSGSEd1M.jpg'
]

const services = [
  { title: 'Абонемент на тренировочные занятия', price: '9 200 ₽', image: shopImages[3] },
  { title: 'Индивидуально/групповые занятия на хоккейном тренажере HST', price: '4 200 ₽', image: shopImages[4] },
  { title: 'Бросковая тренировка', price: 'от 600 ₽', desc: 'В зависимости от количества человек', image: shopImages[1] },
  { title: 'Сборы', price: '40 000 ₽', image: shopImages[2] },
  { title: 'Летний спортивный лагерь', price: '46 000 ₽', image: shopImages[0] },
  { title: 'Командная атрибутика', price: '1 400 ₽', image: shopImages[5] }
]
</script>

<style scoped>
.page {
  padding: 2rem 0 3rem;
}
.page__title {
  font-size: 2rem;
  margin: 0 0 2rem;
}
.abonementy__grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 1.5rem;
  margin-bottom: 2rem;
}
.abonementy-card {
  background: var(--color-surface);
  border: 1px solid var(--color-border);
  border-radius: var(--radius);
  overflow: hidden;
  display: flex;
  flex-direction: column;
}
.abonementy-card__media {
  aspect-ratio: 16/10;
  background: var(--color-surface);
  overflow: hidden;
}
.abonementy-card__img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
}
.abonementy-card__body {
  padding: 1.25rem;
  flex: 1;
  display: flex;
  flex-direction: column;
}
.abonementy-card__type {
  font-size: 1.1rem;
  margin: 0 0 0.5rem;
}
.abonementy-card__price {
  font-size: 1.5rem;
  font-weight: 700;
  margin: 0 0 0.25rem;
}
.abonementy-card__period {
  margin: 0 0 1rem;
  font-size: 0.9rem;
  color: var(--color-text-muted);
}
.abonementy__blocks {
  display: grid;
  gap: 1.5rem;
}
.abonementy__block h3 {
  font-size: 1.1rem;
  margin: 0 0 0.5rem;
}
.abonementy__block p {
  margin: 0;
  color: var(--color-text-muted);
  line-height: 1.5;
}
</style>
