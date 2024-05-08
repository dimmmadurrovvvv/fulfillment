<template>
    <section class="main-page-pricing">

        <header class="main-page-pricing__header">
            <h2 class="main-page-pricing__title">
                Наши цены
            </h2>
            <div class="main-page-pricing__buttons">
                <button class="main-page-pricing__button">
                    <UiIcon name="chevron-left" />
                </button>
                <button class="main-page-pricing__button">
                    <UiIcon name="chevron-right" />
                </button>
            </div>
        </header>

        <ul class="main-page-pricing__list">
            <li class="main-page-pricing__list-item"
                v-for="(card, idx) in cards"
                :key="idx">
                <div class="main-page-pricing__card">
                    <h4 class="main-page-pricing__card-title">
                        {{ card.title }}
                    </h4>

                    <ul class="main-page-pricing__card-services">
                        <li class="main-page-pricing__card-service"
                            v-for="(service, idx) in card.services"
                            :key="idx">
                            <p class="main-page-pricing__card-service-name">
                                {{ service.name }}
                            </p>

                            <span class="main-page-pricing__card-service-separator"></span>

                            <p class="main-page-pricing__card-service-price">
                                {{ service.price }}
                            </p>
                        </li>
                    </ul>

                    <UiButton class="main-page-pricing__card-button"
                        :text="card.button.text"
                        theme="transparent"
                        @click="card.button.callback()" />
                </div>
            </li>
        </ul>
    </section>
</template>

<script setup lang="ts">
const cards = [
    {
        title: 'Логистические услуги',
        services: [
            {
                name: 'Забор товара с рынков Москвы: Южные ворота, Садовод, ТЯК',
                price: 'от 2 000 р'
            },
            {
                name: 'Забор товара по Москве и МО',
                price: 'от 2 000 р'
            },
            {
                name: 'Доставка товара объемом от 1 м3 до 2 м3',
                price: 'от 2 000 р'
            },
        ],
        button: {
            text: 'Подробнее',
            callback: () => { }
        }
    },
    {
        title: 'Услуги по работе с товаром',
        services: [
            {
                name: 'Забор товара с рынков Москвы: Южные ворота, Садовод, ТЯК',
                price: 'от 2 000 р'
            },
            {
                name: 'Забор товара по Москве и МО',
                price: 'от 2 000 р'
            },
            {
                name: 'Доставка товара объемом от 1 м3 до 2 м3',
                price: 'от 2 000 р'
            },
        ],
        button: {
            text: 'Подробнее',
            callback: () => { }
        }
    },
    {
        title: 'Упаковка товара',
        services: [
            {
                name: 'Забор товара с рынков Москвы: Южные ворота, Садовод, ТЯК',
                price: 'от 2 000 р'
            },
            {
                name: 'Забор товара по Москве и МО',
                price: 'от 2 000 р'
            },
            {
                name: 'Доставка товара объемом от 1 м3 до 2 м3',
                price: 'от 2 000 р'
            },
        ],
        button: {
            text: 'Подробнее',
            callback: () => { }
        }
    },
    {
        title: 'Упаковка товара',
        services: [
            {
                name: 'Забор товара с рынков Москвы: Южные ворота, Садовод, ТЯК',
                price: 'от 2 000 р'
            },
            {
                name: 'Забор товара по Москве и МО',
                price: 'от 2 000 р'
            },
            {
                name: 'Доставка товара объемом от 1 м3 до 2 м3',
                price: 'от 2 000 р'
            },
        ],
        button: {
            text: 'Подробнее',
            callback: () => { }
        }
    },
]
</script>

<style scoped lang="scss">
.main-page-pricing {
    @include container;

    &__header {
        @include flex-space-between;
    }

    &__buttons {
        display: flex;
        align-items: center;
    }

    &__button {
        @include flex-all-center;
        @include x-margin-items(12px);

        width: rem(60px);
        height: rem(60px);

        color: $txt-col-primary;
        border-radius: 50%;
        background-color: $fill-col-primary-muted;
    }

    &__title {
        @include font-title;
        @include text-huge;
    }

    &__list {
        display: flex;
        justify-content: space-between;

        margin-top: rem(20px);

        &-item {
            @include flex-item-width(4, 20px);
        }
    }

    &__card {
        display: flex;
        flex-direction: column;

        min-height: rem(830px);
        padding: rem(50px) rem(30px) rem(54px);

        border-radius: rem(30px);
        background-color: $fill-col-primary-muted;

        &-title {
            @include text-big($font-weight-semibold);
        }

        &-services {
            margin-top: rem(22px);
        }

        &-service {
            @include y-margin-items(40px);

            &-name {
                @include text-big($font-weight-regular, $line-height-big);
            }

            &-separator {
                display: inline-block;

                width: 40%;
                height: 1px;

                margin-top: rem(14px);
                margin-bottom: rem(20px);

                background-color: $border-col-secondary;
            }

            &-price {
                font-size: rem(24px);
                font-weight: $font-weight-semibold;
            }
        }

        &-button {
            width: rem(238px);
            margin-top: auto;
        }
    }
}
</style>