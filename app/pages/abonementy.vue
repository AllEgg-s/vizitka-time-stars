<template>
  <div class="page abonementy-page">
    <div class="container">
      <Breadcrumbs :items="[{ title: 'Хоккейная школа', to: '/' }, { title: 'Абонементы' }]" />
      <h1 class="page__title">Абонементы</h1>

      <h2 class="abonementy__subtitle">Стандартные абонементы</h2>
      <p class="abonementy__section-desc">Секция хоккея «Львы ЦХМ»</p>
      <div class="abonementy__grid">
        <article class="abonementy-card">
          <h3 class="abonementy-card__type">Полевой игрок (Стандартный)</h3>
          <p class="abonementy-card__price">15 000 ₽</p>
          <p class="abonementy-card__period">Абонемент на 1 месяц</p>
          <button type="button" class="btn" @click="() => {}">Купить онлайн</button>
        </article>
        <article class="abonementy-card">
          <h3 class="abonementy-card__type">Вратарь (Стандартный)</h3>
          <p class="abonementy-card__price">7 500 ₽</p>
          <p class="abonementy-card__period">Абонемент на 1 месяц</p>
          <button type="button" class="btn" @click="() => {}">Купить онлайн</button>
        </article>
      </div>

      <h2 class="abonementy__subtitle">Льготные абонементы</h2>
      <div class="abonementy__notice">
        <strong>Внимание!</strong> В случае приобретения льготного абонемента необходимо подтверждение права его использования соответствующими документами по согласованию с руководством «Львы ЦХМ». Льготы предоставляются в индивидуальном порядке на основании условий заключенного «Львы ЦХМ» договора возмездного оказания физкультурно-оздоровительных услуг на проведение занятий по хоккею. В противном случае администрация имеет право отказать Вам в предоставлении услуги по льготному тарифу или предоставить услугу в соответствии со Стандартными тарифами Абонементов.
      </div>
      <div class="abonementy__grid">
        <article class="abonementy-card">
          <h3 class="abonementy-card__type">Полевой игрок (Льготный)</h3>
          <p class="abonementy-card__price">13 500 ₽</p>
          <p class="abonementy-card__period">Абонемент на 1 месяц</p>
          <button type="button" class="btn" @click="() => {}">Купить онлайн</button>
        </article>
        <article class="abonementy-card">
          <h3 class="abonementy-card__type">Вратарь (Льготный)</h3>
          <p class="abonementy-card__price">6 750 ₽</p>
          <p class="abonementy-card__period">Абонемент на 1 месяц</p>
          <button type="button" class="btn" @click="() => {}">Купить онлайн</button>
        </article>
      </div>
      <p class="abonementy__note">* льготные абонементы обеспечивают скидку 10% от стоимости стандартного абонемента и предоставляются:</p>
      <ul class="abonementy__list">
        <li>многодетным и малоимущим семьям;</li>
        <li>в случае, если в семье 2 (двое) и более детей занимаются хоккеем в физкультурно-оздоровительных группах «Львы ЦХМ», то таким семьям предоставляется льготный абонемент на второго, третьего и последующих детей.</li>
      </ul>

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
</script>

<style scoped>
.page {
  padding: 2rem 0 3rem;
}
.page__title {
  font-size: 2rem;
  margin: 0 0 2rem;
}
.abonementy__subtitle {
  font-size: 1.5rem;
  margin: 2rem 0 0.5rem;
}
.abonementy__section-desc {
  margin: 0 0 1rem;
  color: var(--color-text-muted);
}
.abonementy__grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
  gap: 1.5rem;
  margin-bottom: 1rem;
}
.abonementy-card {
  background: var(--color-surface);
  border: 1px solid var(--color-border);
  border-radius: var(--radius);
  padding: 1.5rem;
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
.abonementy__notice {
  background: rgba(234, 179, 8, 0.15);
  border: 1px solid rgba(234, 179, 8, 0.5);
  border-radius: var(--radius);
  padding: 1rem;
  margin: 1rem 0;
  font-size: 0.95rem;
  line-height: 1.5;
}
.abonementy__note {
  margin: 1rem 0 0.5rem;
  font-size: 0.9rem;
  color: var(--color-text-muted);
}
.abonementy__list {
  margin: 0 0 2rem;
  padding-left: 1.5rem;
  color: var(--color-text-muted);
  line-height: 1.6;
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
