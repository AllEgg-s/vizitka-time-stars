<template>
    <header class="header">
        <div class="header__top">
            <NuxtLink to="/" class="header__logo">
                <img src="/logo-star-kids.webp" alt="" class="header__logo-img" />
                <span>Время Звезд</span>
            </NuxtLink>
        </div>
        <div class="header__divider"></div>
        <div class="header__nav-row">
            <button
                type="button"
                class="header__burger"
                aria-label="Меню"
                :aria-expanded="menuOpen"
                @click="menuOpen = !menuOpen"
            >
                <span v-if="!menuOpen">menu</span>
                <span v-else>close</span>
            </button>
            <nav class="header__nav" :class="{ 'header__nav--open': menuOpen }">
                <NuxtLink
                    to="/hokkeynaya-shkola"
                    class="header__link"
                    @click="menuOpen = false"
                    >Сведения об образовательной организации</NuxtLink>
                <NuxtLink
                    to="/abonementy"
                    class="header__link"
                    @click="menuOpen = false"
                    >Услуги</NuxtLink>
                <NuxtLink
                    to="/individualnye-trenirovki"
                    class="header__link"
                    @click="menuOpen = false"
                    >Индивидуальные тренировки</NuxtLink>
                <NuxtLink
                    to="/trenery"
                    class="header__link"
                    @click="menuOpen = false"
                    >Тренеры</NuxtLink>
                <NuxtLink
                    to="/kontakty"
                    class="header__link"
                    @click="menuOpen = false"
                    >Контакты</NuxtLink>
            </nav>
        </div>
    </header>
</template>

<script setup lang="ts">
import { ref } from 'vue'
const menuOpen = ref(false)
</script>

<style scoped>
.header {
    background: #1a1a2e;
    color: #eee;
    position: sticky;
    top: 0;
    z-index: 100;
}

.header__top {
    max-width: 1200px;
    margin: 0 auto;
    padding: 1rem 1rem 0 1rem;
    display: flex;
    align-items: center;
    justify-content: space-between;
}

.header__logo {
    display: flex;
    align-items: center;
    gap: 0.75rem;
    font-weight: 700;
    font-size: 1.5rem;
    color: #fff;
    text-decoration: none;
    flex-shrink: 0;
}

.header__logo:hover {
    color: #ccc;
}

.header__logo-img {
    height: 40px;
    width: auto;
    display: block;
}

.header__divider {
    max-width: 1200px;
    margin: 0 auto;
    border-top: 1px solid rgba(255, 255, 255, 0.1);
}

.header__nav-row {
    max-width: 1200px;
    margin: 0 auto;
    padding: 24px 1rem 1rem 1rem;
    display: flex;
    align-items: center;
    gap: 1rem;
}

.header__burger {
    display: none;
    background: transparent;
    border: 1px solid #666;
    color: #fff;
    padding: 0.5rem 0.75rem;
    cursor: pointer;
    border-radius: 4px;
    flex-shrink: 0;
}

.header__nav {
    display: flex;
    gap: 1.5rem;
    align-items: center;
    flex: 1;
    justify-content: space-between;
}

.header__link {
    color: #ddd;
    text-decoration: none;
    white-space: nowrap;
}

.header__link:hover,
.header__link.router-link-active {
    color: #fff;
}

@media (max-width: 768px) {
    .header__top {
        padding: 0.75rem 1rem 0.5rem 1rem;
    }

    .header__nav-row {
        padding: 0.5rem 1rem 0.75rem 1rem;
        gap: 0.5rem;
    }

    .header__burger {
        display: block;
    }

    .header__nav {
        display: none;
        position: absolute;
        top: 100%;
        left: 0;
        right: 0;
        background: #1a1a2e;
        flex-direction: column;
        padding: 1rem;
        gap: 0.5rem;
        flex: none;
    }

    .header__nav--open {
        display: flex;
    }
}
</style>
