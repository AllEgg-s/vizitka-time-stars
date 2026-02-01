<template>
  <div class="page trenery-page">
    <div class="container">
      <Breadcrumbs :items="[{ title: 'Главная', to: '/' }, { title: 'Тренеры' }]" />
      <h1 class="page__title">Тренеры</h1>

      <div class="trenery__grid">
        <article v-for="(coach, i) in coaches" :key="i" class="trenery-card">
          <div class="trenery-card__media">
            <img :src="coach.image" :alt="coach.name" class="trenery-card__img" />
          </div>
          <div class="trenery-card__body">
            <h3 class="trenery-card__name">{{ coach.name }}</h3>
            <a :href="coachTopicUrl" target="_blank" rel="noopener" class="btn">Подробнее</a>
          </div>
        </article>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
definePageMeta({
  layout: 'default'
})

const coachTopicUrl = 'https://vk.ru/topic-125696800_56701933'

const coaches = [
  { name: 'Семён Сергеевич Лямин', image: '/coaches/_u6aU_pb4hc6TgvqzkOUBpqnhAhPO23zFt-TsHqDRCPSIP1jcQ57h_U_MOUb9aiiev_G0eumETQGid5KCDR8PIa0.jpg' },
  { name: 'Кирилл Леонидович Рачёв', image: '/coaches/dy6krtfdNwDEz5pFA8cHLq0bGXZojb5JL3Mh4kbpHjIgvunSA49ydN9zGeHjL-Pp4cZV_mJ2RpquK0gugvY3Pwza.jpg' },
  { name: 'Дмитрий Олегович Вершинин', image: '/coaches/oh_4JtnGs2Dswjo1hZfXbK3kA-dmAEGfsFVZ396wnqzBId1RkzrIKI9pLCY-Hn-SQ1Qu2rkrC9s7wM-LkKwGd1lD.jpg' },
  { name: 'Максим Олегович Вершинин', image: '/coaches/pqX2_np_3mOp0DE-fu_sYOAlcJRkcBs-qfaSF0qnz-btSlDAzuOuNSWVc5OKMzJtaU6Aa6YJVv8lc0zYWO0cBBZ6.jpg' },
  { name: 'Семён Антонович Майков', image: '/coaches/u-7gF0Ca8dfisqbMa47rX3uDMTBTH0OID5VEbum5qaNINZUZShGkz0PaxTpJV4y8Vze32iE-N5UdRpgIGNDByXmd.jpg' }
]
</script>

<style scoped>
.page {
  padding: 2rem 0 3rem;
}
.page__title {
  font-size: 2rem;
  margin: 0 0 1.5rem;
}
.trenery__grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
  gap: 1.5rem;
}
.trenery-card {
  background: var(--color-surface);
  border: 1px solid var(--color-border);
  border-radius: var(--radius);
  overflow: hidden;
  display: flex;
  flex-direction: column;
}
.trenery-card__media {
  aspect-ratio: 3/4;
  background: var(--color-surface);
  overflow: hidden;
}
.trenery-card__img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
}
.trenery-card__body {
  padding: 1.25rem;
  flex: 1;
  display: flex;
  flex-direction: column;
  gap: 1rem;
}
.trenery-card__name {
  font-size: 1.25rem;
  margin: 0;
}
</style>
