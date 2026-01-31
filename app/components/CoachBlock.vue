<template>
  <section class="coach section">
    <div class="container coach__inner">
      <div class="coach__media">
        <div class="media-placeholder">Тут может быть картинка</div>
      </div>
      <div class="coach__content">
        <h2 class="coach__name">Дмитрий Александрович Лисов</h2>
        <p class="coach__role">Старший тренер</p>
        <button type="button" class="btn" @click="showQuestionForm = true">Задать вопрос</button>
      </div>
      <div v-if="showQuestionForm" class="coach__modal">
        <div class="coach__modal-inner">
          <h3>Задать вопрос тренеру</h3>
          <LeadForm @success="showQuestionForm = false; questionSent = true" />
          <button type="button" class="btn btn--secondary" @click="showQuestionForm = false">Закрыть</button>
        </div>
      </div>
      <p v-if="questionSent" class="coach__sent">Спасибо! Мы получили Ваш вопрос и тренер ответит на него в ближайшее время. Ожидайте ответ на Вашу почту.</p>
    </div>
  </section>
</template>

<script setup lang="ts">
const showQuestionForm = ref(false)
const questionSent = ref(false)
</script>

<style scoped>
.coach__inner {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 2rem;
  align-items: center;
}
.coach__media {
  aspect-ratio: 1;
  max-width: 300px;
  background: var(--color-surface);
  border: 1px solid var(--color-border);
  border-radius: var(--radius);
  display: flex;
  align-items: center;
  justify-content: center;
  color: var(--color-text-muted);
  font-size: 0.9rem;
}
.coach__name {
  font-size: 1.5rem;
  margin: 0 0 0.25rem;
}
.coach__role {
  margin: 0 0 1rem;
  color: var(--color-text-muted);
}
.coach__modal {
  position: fixed;
  inset: 0;
  background: rgba(0,0,0,0.7);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 200;
  padding: 1rem;
}
.coach__modal-inner {
  background: var(--color-surface);
  padding: 2rem;
  border-radius: var(--radius);
  max-width: 420px;
  width: 100%;
}
.coach__modal-inner h3 {
  margin: 0 0 1rem;
}
.coach__sent {
  grid-column: 1 / -1;
  color: #22c55e;
}
.btn--secondary {
  background: var(--color-border);
  margin-top: 1rem;
}
@media (max-width: 768px) {
  .coach__inner {
    grid-template-columns: 1fr;
  }
}
</style>
