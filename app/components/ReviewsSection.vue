<template>
  <section class="reviews section">
    <div class="container">
      <h2 class="section-title">Отзывы о нас</h2>
      <ClientOnly>
        <div class="reviews__slider-wrap">
          <Swiper
            :modules="modules"
            :navigation="{ nextEl: '.reviews__next', prevEl: '.reviews__prev' }"
            class="reviews-swiper"
          >
            <SwiperSlide v-for="(r, i) in reviews" :key="i">
              <article class="review-card">
                <div class="review-card__avatar">
                  <span>Тут должна быть картинка</span>
                </div>
                <div class="review-card__body">
                  <h3 class="review-card__author">{{ r.author }}</h3>
                  <p class="review-card__text">{{ r.text }}</p>
                </div>
              </article>
            </SwiperSlide>
          </Swiper>
          <div class="reviews__nav">
            <button type="button" class="reviews__btn reviews__prev" aria-label="Назад">‹</button>
            <button type="button" class="reviews__btn reviews__next" aria-label="Вперед">›</button>
          </div>
        </div>
      </ClientOnly>
      <div class="reviews__action">
        <button type="button" class="btn" @click="showReviewForm = true">Отправить Ваш отзыв</button>
      </div>
      <div v-if="showReviewForm" class="reviews__modal">
        <div class="reviews__modal-inner">
          <h3>Отправить отзыв</h3>
          <LeadForm @success="showReviewForm = false; reviewSent = true" />
          <button type="button" class="btn btn--secondary" @click="showReviewForm = false">Закрыть</button>
        </div>
      </div>
      <p v-if="reviewSent" class="reviews__sent">Спасибо! Отзыв отправлен на модерацию и будет опубликован после проверки.</p>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import { Swiper, SwiperSlide } from 'swiper/vue'
import { Navigation } from 'swiper/modules'
import 'swiper/css'
import 'swiper/css/navigation'

const modules = [Navigation]

const reviews = [
  { author: 'Наталья', meta: 'сын Алексей, 9 лет', text: 'Занимаемся второй год у Дмитрия Ивановича, очень довольны результатом. Ребенок болеет хоккеем, стал более рассудительным, спокойным. На занятия спешит, приходит уставший, но очень довольный. От телевизора, когда идет какой-нибудь хоккейный матч теперь не оторвать, смотрит, комментирует что-то, кого-то хвалит, кого-то ругает ))' },
  { author: 'Елена', meta: 'сын Владимир, 11 лет', text: 'Хоккей стал самой важной частью нашей жизни, теперь мы все дружно в нем разбираемся. Команда для Володи - как вторая семья, тренер - как крестный, наверное. Очень сильная школа, оказывается хоккей - это не только спорт, это целая философия. Уже есть маленькие, но такие важные для нас достижения. Полное взаимопонимание и с тренером, и с командой. Спасибо!' },
  { author: 'Наталья', meta: 'сын Иван, 5 лет', text: 'Нам всего 5 лет, очень переживали, что не получится. Спасибо тренерам, очень быстро поставили Ваню на коньки. Все терпеливые, внимательные, видно, что любят детей и умеют с ними находить общий язык. Работой центра прям сильно довольны! Тренеры - большие профессионалы! Ребенка стал более уверенным после занятий, полюбил хоккей и хочет заниматься дальше!' }
]
const showReviewForm = ref(false)
const reviewSent = ref(false)
</script>

<style scoped>
.reviews__slider-wrap {
  position: relative;
}
.reviews-swiper {
  padding-bottom: 0.5rem;
}
.review-card {
  display: grid;
  grid-template-columns: auto 1fr;
  gap: 1.5rem;
  align-items: start;
  background: var(--color-surface);
  border-radius: var(--radius);
  padding: 1.5rem;
  border: 1px solid var(--color-border);
  min-height: 180px;
}
.review-card__avatar {
  width: 80px;
  height: 80px;
  flex-shrink: 0;
  border-radius: 50%;
  background: #252540;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 0.65rem;
  color: var(--color-text-muted);
  text-align: center;
  padding: 0.5rem;
}
.review-card__body {
  min-width: 0;
}
.review-card__author {
  margin: 0 0 0.5rem;
  font-size: 1.1rem;
}
.review-card__text {
  margin: 0;
  font-size: 0.95rem;
  line-height: 1.5;
  color: var(--color-text-muted);
}
.reviews__nav {
  display: flex;
  justify-content: center;
  gap: 1rem;
  margin-top: 1rem;
}
.reviews__btn {
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
.reviews__btn:hover:not(:disabled) {
  background: var(--color-border);
}
.reviews__btn.swiper-button-disabled {
  opacity: 0.4;
  cursor: default;
}
.reviews__action {
  text-align: center;
  margin-top: 2rem;
}
.reviews__modal {
  position: fixed;
  inset: 0;
  background: rgba(0,0,0,0.7);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 200;
  padding: 1rem;
}
.reviews__modal-inner {
  background: var(--color-surface);
  padding: 2rem;
  border-radius: var(--radius);
  max-width: 420px;
  width: 100%;
}
.reviews__modal-inner h3 {
  margin: 0 0 1rem;
}
.reviews__sent {
  text-align: center;
  color: #22c55e;
  margin-top: 1rem;
}
.btn--secondary {
  background: var(--color-border);
  margin-top: 1rem;
}
</style>
