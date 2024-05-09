<template>
    <header class="header">
        <div class="header__inner">
            <div class="header__col">
                <LayoutLogo />
            </div>
            <div class="header__col">
                <nav class="header__nav">
                    <ul class="header__nav-links">
                        <li class="header__nav-links-item"
                            v-for="(link, idx) in headerLinks"
                            :key="idx">
                            <NuxtLink class="header__nav-links-item-link"
                                :to="link.path">
                                {{ link.text }}
                            </NuxtLink>
                        </li>
                    </ul>
                </nav>
            </div>
            <div class="header__col">
                <div class="header__meta">
                    <a class="header__meta-tel"
                        href="tel:+74959999999">
                        +7 495 999-99-99
                    </a>
                </div>
            </div>
        </div>
    </header>
</template>

<script setup lang="ts">

const headerLinks = [
    { text: 'О нас', path: '#' },
    { text: 'Наш склад', path: '#' },
    { text: 'Наши услуги', path: '#' },
    { text: 'Наши цены', path: '#' },
    { text: 'FAQ', path: '#' },
    { text: 'Связь с нами', path: '#' },
]
</script>

<style scoped lang="scss">
.header {
    height: rem($header-height-desktop);

    box-shadow: $box-shadow-default;
    background-color: $fill-col-primary;

    &__inner {
        @include flex-space-between;
        @include container;

        height: 100%;
    }

    &__col {}

    &__nav {
        &-links {
            display: flex;
            align-items: center;

            &-item {
                @include x-margin-items(0);

                &-link {
                    @include text-normal;

                    padding: 1px rem(10px);
                    font-weight: 600;
                }
            }
        }
    }

    &__meta {
        &-tel {
            @include font-title;
            @include text-normal;
        }
    }
}
</style>