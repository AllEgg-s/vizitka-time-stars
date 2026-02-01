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
                  <img v-if="item.image" :src="item.image" :alt="item.title || 'Новость'" class="news-card__img" />
                  <div v-else class="media-placeholder">Тут может быть картинка</div>
                </div>
                <div class="news-card__body">
                  <p class="news-card__text">{{ item.excerpt }}</p>
                  <a :href="item.url" target="_blank" rel="noopener" class="btn btn--small">Подробнее</a>
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
  {
    image: '/news/iGWLwzjYoJVAGUUeCd3kaRr1eyi6lNTIndt-h_jA0q9PbaMTs7Sg5Va9IzKiU9P_W5cuZvgYPu2bNarPhKeQlfrb.jpg',
    excerpt: `🎄✨ С Наступающим Новым годом, друзья!

Уходящий год подарил нам много эмоций, ярких моментов и важных шагов вперёд 🏒

Спасибо родителям — за поддержку, веру и силы, которые вы вкладываете в своих детей ❤
И особые слова благодарности ребятам: за характер, труд и стремление становиться лучше каждый день. Именно с вас начинается будущее хоккея 💪✨

Пусть 2026 год принесёт новые возможности, яркие победы и моменты, которыми захочется гордиться. Пусть он будет наполнен радостью, уверенностью в себе и настоящими хоккейными эмоциями 🥅

🏆 Мы продолжаем расти, развиваться и воспитывать чемпионов!
Спасибо, что этот путь мы проходим вместе!`,
    url: 'https://vk.ru/wall-125696800_1317'
  },
  {
    image: '/news/VlIywi--zCXcJuO2YrgbYz3GUKR4zwLvig9xXCO2XPGBo8dVYehPgA6glxfptYVVvef2gvzRT3ePCgLX0_NJ4adS.jpg',
    excerpt: `❄️ Этот предновогодний турнир по хоккею 🏒 на кубок Деда 🎅 Мороза стал для нас уже настоящей ❤️ традицией, превращаясь в яркое и незабываемое событие каждого года. Именно в этот особенный период зимы атмосфера праздника 🎄 и ожидания чуда наполняет наши соревнования особой теплотой и магией 🪄.

Множество команд и болельщиков собрались в ледовом дворце ГУОР по хоккею, чтобы подарить друг другу заряд позитива и спортивного духа. ☝️ Каждый матч отличался борьбой до последней секунды, а атмосфера приближающегося праздника сделала всё ещё более ярким 🤩 и захватывающим.

📣 По итогам турнира:
🥇 ХК «ВРЕМЯ ЗВЕЗД»
🥈 ХК «ОГНЕННЫЕ ЛИСЫ»
🥉 ХК «ИМПУЛЬС»
🏅 ХК «ИСКРА»
🏅 ХК «ЗВЕЗДА»

Огромное спасибо 🙏 всем участникам — за волю к победе и нереальный азарт. Особая 😊 благодарность зрителям, чья поддержка вдохновляла игроков и создавала атмосферу настоящего спортивного праздника 🫶.

🤗 Мы с радостью ждем вас в январе ❄️, чтобы снова выйти на лёд и побороться за лидерство 💪!

Пусть НОВЫЙ 🎄 ГОД принесет еще больше ярких побед, незабываемых моментов и праздничного настроения! УРА 🎉!`,
    url: 'https://vk.ru/wall-125696800_1316'
  }
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
  overflow: hidden;
}
.news-card__img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
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
  white-space: pre-line;
  max-height: 320px;
  overflow-y: auto;
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
