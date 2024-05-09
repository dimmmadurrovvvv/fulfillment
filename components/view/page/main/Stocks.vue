<template>
    <section class="main-page-stocks">
        <div class="main-page-stocks__meta">
            <h2 class="main-page-stocks__meta-title">
                Складские помещения
            </h2>
            <p class="main-page-stocks__meta-subtitle">
                Мы понимаем, что работа с маркетплейсами требует быстрого и точного выполнения заказов
            </p>
        </div>

        <div class="main-page-stocks__main">
            <div class="main-page-stocks__content">
                <ul class="main-page-stocks__cards">
                    <li class="main-page-stocks__cards-item"
                        v-for="card in cards"
                        :key="card.title">
                        <div class="main-page-stocks__card">
                            <h3 class="main-page-stocks__card-title">
                                {{ card.title }} <span v-if="card.mark"
                                    class="main-page-stocks__card-title--mark">
                                    {{ card.mark }}
                                </span>
                            </h3>
                            <p class="main-page-stocks__card-description">
                                {{ card.description }}
                            </p>
                        </div>
                    </li>
                </ul>

                <UiButton class="main-page-stocks__details-button"
                    text="Узнать больше"
                    theme="transparent" />
            </div>

            <div class="main-page-stocks__image">
                <img class="main-page-stocks__image-pic"
                    src="/images/static/stock-image.png"
                    alt="Фото склада">

            </div>
        </div>
    </section>
</template>

<script setup lang="ts">
const cards = [
    { title: '1 000', mark: 'м²', description: 'площадь склада' },
    { title: '50+', description: 'сотрудников склада' },
]
</script>

<style scoped lang="scss">
.main-page-stocks {
    @include container;

    display: flex;
    flex-direction: column;

    &__meta {
        @include flex-space-between;

        &-title {
            @include font-title;
            @include text-huge;
        }

        &-subtitle {
            @include text-big($font-weight-medium, $line-height-medium);

            max-width: 30%;

            text-align: end;
        }
    }

    &__main {
        display: flex;

        margin-top: rem(20px);
    }

    &__content {
        width: rem(460px);
    }

    &__cards {
        &-item {
            @include y-margin-items(20px);
        }
    }

    &__card {
        padding: rem(30px) rem(35px) rem(14px);

        border-radius: rem($border-radius-medium);
        background-color: $fill-col-secondary;

        &-title {
            @include text-huge;
            @include font-title;

            &--mark {
                @include text-great;
            }
        }

        &-description {
            @include text-big;

            margin-top: rem(16px);
        }
    }

    &__details-button {
        margin-top: rem(100px);
    }

    &__image {
        position: relative;

        flex-grow: 1;
        overflow: hidden;

        margin-left: rem(36px);

        border-radius: rem($border-radius-medium);

        &-pic {
            @include absolute-all-null;
            @include object-cover-full;
        }
    }
}
</style>