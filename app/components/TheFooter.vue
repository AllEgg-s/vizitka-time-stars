<template>
  <footer class="footer">
    <div class="footer__inner">
      <div class="footer__top">
        <NuxtLink to="/" class="footer__logo">ЦХМ</NuxtLink>
        <div class="footer__contacts">
          <a :href="`tel:${phoneRaw}`" class="footer__phone">{{ phone }}</a>
          <span class="footer__hours">{{ hours }}</span>
          <span class="footer__address">{{ address }}</span>
          <a :href="`mailto:${email}`" class="footer__email">{{ email }}</a>
        </div>
        <nav class="footer__nav">
          <NuxtLink to="/hokkeynaya-shkola">Хоккейная школа</NuxtLink>
          <NuxtLink to="/abonementy">Абонементы</NuxtLink>
          <NuxtLink to="/arenda">Аренда</NuxtLink>
          <NuxtLink to="/individualnye-trenirovki">Индивидуальные тренировки</NuxtLink>
          <NuxtLink to="/trenery">Тренеры</NuxtLink>
          <NuxtLink to="/kontakty">Контакты</NuxtLink>
        </nav>
      </div>
      <div class="footer__bottom">
        <span class="footer__copy">© 2026, Центр хоккейного мастерства</span>
        <span class="footer__legal">
          <a href="#">Договор-оферта</a>
          <a href="#">Политика конфиденциальности</a>
        </span>
      </div>
    </div>
  </footer>
</template>

<script setup lang="ts">
const phone = '+7 (495) 323-88-87'
const phoneRaw = '74953238887'
const hours = 'Ежедневно с 6:00 до 24:00'
const address = 'Москва, Митино, Айс Арена ЦХМ'
const email = 'info@hockey-chm.ru'
</script>

<style scoped>
.footer {
  background: #1a1a2e;
  color: #aaa;
  padding: 2rem 1rem 1rem;
  margin-top: auto;
}
.footer__inner {
  max-width: 1200px;
  margin: 0 auto;
}
.footer__top {
  display: grid;
  grid-template-columns: auto 1fr auto;
  gap: 2rem;
  align-items: start;
  padding-bottom: 1.5rem;
  border-bottom: 1px solid #333;
}
.footer__logo {
  font-weight: 700;
  font-size: 1.5rem;
  color: #fff;
  text-decoration: none;
}
.footer__contacts {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}
.footer__phone,
.footer__email {
  color: #fff;
  text-decoration: none;
}
.footer__email:hover,
.footer__phone:hover {
  text-decoration: underline;
}
.footer__nav {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}
.footer__nav a {
  color: #aaa;
  text-decoration: none;
}
.footer__nav a:hover {
  color: #fff;
}
.footer__bottom {
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  gap: 1rem;
  padding-top: 1rem;
  font-size: 0.875rem;
}
.footer__legal a {
  color: #888;
  text-decoration: none;
  margin-left: 1rem;
}
.footer__legal a:hover {
  color: #fff;
}
@media (max-width: 768px) {
  .footer__top {
    grid-template-columns: 1fr;
  }
}
</style>
