<template>
  <div>
    <HeroSection />
    <LionsBlock />
    <BenefitsSection />
    <ArenaSlider />
    <ReviewsSection />
    <FaqSection />
    <CoachBlock />
    <PartnersSection />
    <MapSection />
    <section class="contact-form section">
      <div class="container">
        <h2 class="section-title">Остались вопросы?</h2>
        <p class="contact-form__hint">Звоните по телефону +7 (495) 323-88-87 или заполните форму, и наш менеджер свяжется с Вами.</p>
        <LeadForm />
      </div>
    </section>
  </div>
</template>

<script setup lang="ts">
definePageMeta({
  layout: 'default'
})
</script>

<style scoped>
.contact-form.section {
  padding: 3rem 0;
}
.contact-form__hint {
  text-align: center;
  margin: 0 0 1.5rem;
  color: var(--color-text-muted);
}
</style>
