<template>
  <section class="news section">
    <div class="container">
      <h2 class="section-title">Новости</h2>
      <ClientOnly>
        <div class="news__slider-wrap">
          <Swiper
            :modules="modules"
            :navigation="{ nextEl: '.news__next', prevEl: '.news__prev' }"
            class="news-swiper"
          >
            <SwiperSlide v-for="(item, i) in newsItems" :key="i">
              <article class="news-card">
                <div class="news-card__media">
                  <div class="media-placeholder">Тут может быть картинка</div>
                </div>
                <div class="news-card__body">
                  <p class="news-card__text">{{ item.excerpt }}</p>
                  <NuxtLink :to="item.url" class="btn btn--small">Подробнее</NuxtLink>
                </div>
              </article>
            </SwiperSlide>
          </Swiper>
          <div class="news__nav">
            <button type="button" class="news__btn news__prev" aria-label="Назад">‹</button>
            <button type="button" class="news__btn news__next" aria-label="Вперед">›</button>
          </div>
        </div>
      </ClientOnly>
    </div>
  </section>
</template>

<script setup lang="ts">
import { Swiper, SwiperSlide } from 'swiper/vue'
import { Navigation } from 'swiper/modules'
import 'swiper/css'
import 'swiper/css/navigation'

const modules = [Navigation]

const newsItems = [
  { title: 'Открытие сезона', excerpt: 'Приглашаем на открытие сезона 2025/26. Торжественное мероприятие состоится в конце сентября.', url: '#' },
  { title: 'Набор в группы', excerpt: 'Идёт набор в детские группы по хоккею. Запись на просмотр открыта для детей 2017 г.р. и старше.', url: '#' },
  { title: 'Тренировки на льду', excerpt: 'Регулярные тренировки на льду Арены ГУОР. Расписание и условия посещения — в разделе Услуги.', url: '#' }
]
</script>

<style scoped>
.news__slider-wrap {
  position: relative;
}
.news-swiper {
  padding-bottom: 0.5rem;
}
.news-card {
  background: var(--color-surface);
  border-radius: var(--radius);
  overflow: hidden;
  border: 1px solid var(--color-border);
  display: flex;
  flex-direction: column;
  min-height: 320px;
}
.news-card__media {
  aspect-ratio: 16/10;
  background: #252540;
  display: flex;
  align-items: center;
  justify-content: center;
  color: var(--color-text-muted);
  font-size: 0.85rem;
}
.news-card__body {
  padding: 1.25rem;
  flex: 1;
  display: flex;
  flex-direction: column;
  gap: 1rem;
}
.news-card__text {
  margin: 0;
  font-size: 0.95rem;
  line-height: 1.5;
  color: var(--color-text-muted);
  flex: 1;
}
.news__nav {
  display: flex;
  justify-content: center;
  gap: 1rem;
  margin-top: 1rem;
}
.news__btn {
  width: 44px;
  height: 44px;
  display: flex;
  align-items: center;
  justify-content: center;
  background: var(--color-surface);
  border: 1px solid var(--color-border);
  color: var(--color-text);
  border-radius: var(--radius);
  cursor: pointer;
  font-size: 1.5rem;
  line-height: 1;
}
.news__btn:hover:not(:disabled) {
  background: var(--color-border);
}
.news__btn.swiper-button-disabled {
  opacity: 0.4;
  cursor: default;
}
.btn--small {
  padding: 0.5rem 1rem;
  font-size: 0.9rem;
  align-self: flex-start;
}
</style>
