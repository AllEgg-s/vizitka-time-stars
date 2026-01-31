<template>
    <header class="header">
        <div class="header__top">
            <NuxtLink to="/" class="header__logo">ЦХМ</NuxtLink>
            <div class="header__contacts">
                <a :href="`tel:${phoneRaw}`" class="header__phone">{{
                    phone
                }}</a>
                <span class="header__hours">{{ hours }}</span>
            </div>
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
                    >Хоккейная школа</NuxtLink
                >
                <NuxtLink
                    to="/abonementy"
                    class="header__link"
                    @click="menuOpen = false"
                    >Абонементы</NuxtLink
                >
                <NuxtLink
                    to="/arenda"
                    class="header__link"
                    @click="menuOpen = false"
                    >Аренда</NuxtLink
                >
                <NuxtLink
                    to="/individualnye-trenirovki"
                    class="header__link"
                    @click="menuOpen = false"
                    >Индивидуальные тренировки</NuxtLink
                >
                <NuxtLink
                    to="/trenery"
                    class="header__link"
                    @click="menuOpen = false"
                    >Тренеры</NuxtLink
                >
                <NuxtLink
                    to="/kontakty"
                    class="header__link"
                    @click="menuOpen = false"
                    >Контакты</NuxtLink
                </NuxtLink>
            </nav>
        </div>
    </header>
</template>

<script setup lang="ts">
const phone = '+7 (495) 323-88-87'
const phoneRaw = '74953238887'
const hours = 'Ежедневно, с 06:00 до 24:00'

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
    font-weight: 700;
    font-size: 1.5rem;
    color: #fff;
    text-decoration: none;
    flex-shrink: 0;
}

.header__logo:hover {
    color: #ccc;
}

.header__contacts {
    display: flex;
    flex-direction: column;
    align-items: flex-end;
    gap: 0.25rem;
    text-align: right;
    flex-shrink: 0;
}

.header__phone {
    color: #fff;
    text-decoration: none;
    font-weight: 600;
}

.header__phone:hover {
    text-decoration: underline;
}

.header__hours {
    font-size: 0.875rem;
    color: #aaa;
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
