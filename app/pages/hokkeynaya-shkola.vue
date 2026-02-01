<template>
  <div class="page hokkeynaya-shkola-page">
    <div class="container">
      <Breadcrumbs :items="[{ title: 'Главная', to: '/' }, { title: 'Сведения об образовательной организации' }]" />
      <h1 class="page__title">Сведения об образовательной организации</h1>
      <div class="school__intro">
        <p><strong>ЦЕНТР ХОККЕЙНОГО МАСТЕРСТВА (ЦХМ)</strong> создан в 2014 году для воспитания профессиональных хоккеистов!</p>
        <p>На сегодняшний день «Львы ЦХМ» — первая и единственная в России коммерческая школа, заявленная всеми возрастами в чемпионаты и первенства города Москвы!</p>
        <p>Тренировочный процесс и домашние игры проходят в новом многофункциональном спортивном комплексе «Митино Айс Арена ЦХМ».</p>
        <p>Наша хоккейная школа принимает участие в официальных соревнованиях, проводимых Федерацией Хоккея Москвы (ФХМ).</p>
      </div>
      <div class="school__cta">
        <p class="school__cta-text">Идет набор 2014-2020 г.р.</p>
        <p class="school__cta-price">Стоимость абонемента от 6 750 руб.</p>
        <NuxtLink to="/abonementy" class="btn">Купить абонемент</NuxtLink>
      </div>
      <div class="school__media">
        <div class="media-placeholder">Тут может быть картинка</div>
      </div>
      <h2 class="school__subtitle">Для развития созданы отличные условия:</h2>
      <ul class="school__conditions">
        <li>два больших льда;</li>
        <li>залы функциональной подготовки;</li>
        <li>игровые залы;</li>
        <li>бросковые зоны;</li>
        <li>зоны конькобежных тренажёров HST.</li>
      </ul>
      <div class="school__outro">
        <p>Тренировки спортсменов проходят в группах по году рождения для детей от 3-х до 17-ти лет.</p>
        <p>Продолжительность тренировок для детей составляет 75-90 минут и проводятся от пяти раз в неделю (лед+ОФП).</p>
        <p>Обучение в школе платное. Начиная с 8 лет, наиболее перспективные воспитанники переводятся на полное обеспечение хоккейным клубом.</p>
      </div>
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
  margin: 0 0 1.5rem;
}
.school__intro p {
  margin: 0 0 1rem;
  line-height: 1.6;
  color: var(--color-text-muted);
}
.school__cta {
  background: var(--color-surface);
  border: 1px solid var(--color-border);
  border-radius: var(--radius);
  padding: 1.5rem;
  margin: 2rem 0;
}
.school__cta-text {
  margin: 0 0 0.25rem;
  font-size: 1.1rem;
}
.school__cta-price {
  margin: 0 0 1rem;
  color: var(--color-text-muted);
}
.school__media {
  aspect-ratio: 16/9;
  max-width: 700px;
  margin-bottom: 2rem;
  background: var(--color-surface);
  border: 1px solid var(--color-border);
  border-radius: var(--radius);
  display: flex;
  align-items: center;
  justify-content: center;
  color: var(--color-text-muted);
  font-size: 0.95rem;
}
.school__subtitle {
  font-size: 1.25rem;
  margin: 0 0 1rem;
}
.school__conditions {
  margin: 0 0 2rem;
  padding-left: 1.5rem;
  line-height: 1.7;
  color: var(--color-text-muted);
}
.school__outro p {
  margin: 0 0 1rem;
  line-height: 1.6;
  color: var(--color-text-muted);
}
</style>
