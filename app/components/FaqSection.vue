<template>
  <section class="faq section">
    <div class="container">
      <h2 class="section-title">Ответы на вопросы родителей</h2>
      <div class="faq__list">
        <div
          v-for="(item, i) in items"
          :key="i"
          class="faq__item"
          :class="{ 'faq__item--open': openIndex === i }"
        >
          <button
            type="button"
            class="faq__question"
            :aria-expanded="openIndex === i"
            @click="toggle(i)"
          >
            {{ item.question }}
            <span class="faq__arrow">{{ openIndex === i ? '▲' : '▼' }}</span>
          </button>
          <div v-show="openIndex === i" class="faq__answer">
            <p>{{ item.answer }}</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
const items = [
  { question: 'Со скольки лет можно отдавать ребенка в хоккейную школу?', answer: 'Общая практика показывает, что лучший возраст для ребенка начать заниматься хоккеем, это 3-4 года!' },
  { question: 'Как часто у вас проводится набор в детские группы?', answer: 'В нашей школе набор для младшего возраста идет круглый год. Так же круглый год идут просмотры в команды старших возрастов.' },
  { question: 'Сколько раз в неделю лучше посещать тренировки для детей 3-х лет?', answer: 'В этом возрасте закладывается фундамент хоккейных навыков, для ребенка лучше всего будет 5/6 раз в неделю приходить на занятия.' },
  { question: 'Как понять готов ли ребенок к групповым тренировкам или нет?', answer: 'Посмотреть, как ребенок ведет себя в группе детей, как коммуницирует с другими детьми. А лучше прийти и попробовать, наши опытные тренеры подскажут и направят вашего ребенка в правильном направлении, и они обзаведутся новыми друзьями!' },
  { question: 'Если во время тренировки ребенок начинает плакать, что делать?', answer: 'Первое-без паники, наши тренеры направят и отвлекут вашего ребенка. Бывает, что ребенку не хватает внимания родителей, зрительного контакта с ними, поэтому лучше всего родителям поменьше присутствовать близко ко льду, ребёнок будет учиться самостоятельности!' },
  { question: 'Какие документы нужны, чтобы записать ребенка на занятия?', answer: 'Для записи ребенка будет достаточно следующих документов: справка врача о допуске, спортивная страховка, копия свидетельства о рождении.' },
  { question: 'Сколько времени длится занятие и сколько детей занимается в группе?', answer: 'Занятие длится один час. Три раза в неделю после занятий на льду проводится час общефизической подготовки.' },
  { question: 'Работает ли школа в период летних каникул?', answer: 'Сезон заканчивается 28 мая, начинается 10 июля. В перерыве набираются группы желающих заниматься и работает дежурный тренерский состав.' }
]
const openIndex = ref<number | null>(0)

function toggle(i: number) {
  openIndex.value = openIndex.value === i ? null : i
}
</script>

<style scoped>
.faq__list {
  max-width: 700px;
  margin: 0 auto;
}
.faq__item {
  border: 1px solid var(--color-border);
  border-radius: var(--radius);
  margin-bottom: 0.5rem;
  overflow: hidden;
  background: var(--color-surface);
}
.faq__question {
  width: 100%;
  padding: 1rem 1.25rem;
  text-align: left;
  background: transparent;
  border: none;
  color: var(--color-text);
  font-size: 1rem;
  cursor: pointer;
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 1rem;
}
.faq__question:hover {
  background: rgba(255,255,255,0.05);
}
.faq__arrow {
  flex-shrink: 0;
  font-size: 0.75rem;
  color: var(--color-text-muted);
}
.faq__answer {
  padding: 0 1.25rem 1rem;
  border-top: 1px solid var(--color-border);
}
.faq__answer p {
  margin: 0;
  padding-top: 0.75rem;
  color: var(--color-text-muted);
  line-height: 1.5;
}
</style>
