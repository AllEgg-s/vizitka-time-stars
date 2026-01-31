<template>
  <section class="arena section">
    <div class="container">
      <h2 class="section-title">Арена ЦХМ</h2>
      <ClientOnly>
        <Swiper
          :effect="'cards'"
          :grab-cursor="true"
          :modules="modules"
          class="arena-swiper"
        >
          <SwiperSlide v-for="i in 9" :key="i">
            <div class="arena__placeholder">Тут может быть картинка</div>
          </SwiperSlide>
        </Swiper>
      </ClientOnly>
    </div>
  </section>
</template>

<script setup lang="ts">
import { Swiper, SwiperSlide } from 'swiper/vue'
import { EffectCards } from 'swiper/modules'
import 'swiper/css'
import 'swiper/css/effect-cards'

const modules = [EffectCards]
</script>

<style scoped>
.arena-swiper {
  width: 100%;
  max-width: 420px;
  margin: 0 auto;
  padding: 1rem 0;
}
.arena-swiper :deep(.swiper-slide) {
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: var(--radius);
  background: var(--color-surface);
  border: 1px solid var(--color-border);
}
.arena__placeholder {
  width: 100%;
  aspect-ratio: 16/10;
  display: flex;
  align-items: center;
  justify-content: center;
  color: var(--color-text-muted);
  font-size: 0.9rem;
}
</style>
