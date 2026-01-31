<template>
  <section class="partners section">
    <div class="container">
      <h2 class="section-title">Партнёры</h2>
      <ClientOnly>
        <div class="partners__slider-wrap">
          <Swiper
            :modules="modules"
            :navigation="{ nextEl: '.partners__next', prevEl: '.partners__prev' }"
            :slides-per-view="2"
            :space-between="24"
            :breakpoints="{ 640: { slidesPerView: 3 }, 900: { slidesPerView: 4 } }"
            class="partners-swiper"
          >
            <SwiperSlide v-for="i in 4" :key="i">
              <div class="partners__item">
                <div class="media-placeholder">Тут может быть логотип</div>
              </div>
            </SwiperSlide>
          </Swiper>
          <div class="partners__nav">
            <button type="button" class="partners__btn partners__prev" aria-label="Назад">‹</button>
            <button type="button" class="partners__btn partners__next" aria-label="Вперед">›</button>
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
</script>

<style scoped>
.partners__slider-wrap {
  position: relative;
}
.partners-swiper {
  padding-bottom: 0.5rem;
}
.partners__item {
  width: 100%;
  max-width: 180px;
  margin: 0 auto;
  aspect-ratio: 2/1;
  background: var(--color-surface);
  border: 1px solid var(--color-border);
  border-radius: var(--radius);
  display: flex;
  align-items: center;
  justify-content: center;
  color: var(--color-text-muted);
  font-size: 0.8rem;
  text-align: center;
}
.partners__nav {
  display: flex;
  justify-content: center;
  gap: 1rem;
  margin-top: 1rem;
}
.partners__btn {
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
.partners__btn:hover:not(:disabled) {
  background: var(--color-border);
}
.partners__btn.swiper-button-disabled {
  opacity: 0.4;
  cursor: default;
}
</style>
