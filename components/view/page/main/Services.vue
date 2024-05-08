<template>
    <section class="main-page-services">
        <ul class="main-page-services__list">
            <li class="main-page-services__list-item"
                :class="{ 'big': card?.big }"
                v-for="(card, idx) in cards"
                :key="idx">
                <div class="main-page-services__card">
                    <div class="main-page-services__card-inner">
                        <h3 v-if="card.title"
                            class="main-page-services__card-title">
                            {{ card.title }}
                        </h3>

                        <h4 v-if="card.subtitle"
                            class="main-page-services__card-subtitle">
                            {{ card.subtitle }}
                        </h4>

                        <p v-if="card.description"
                            class="main-page-services__card-description">
                            {{ card.description }}
                        </p>

                        <UiButton v-if="card.button"
                            class="main-page-services__card-details-button"
                            :text="card.button.text"
                            theme="transparent"
                            @click="onCardButtonClick(card.button.callback)" />
                    </div>

                    <div v-if="card.image"
                        class="main-page-services__card-image">
                        <img class="main-page-services__card-image-pic"
                            :src="card.image"
                            alt="Иллюстрация карточки">
                    </div>
                </div>
            </li>
        </ul>
        <LazyViewPopupBase v-model="showPopup"
            title="Логистические услуги" />
    </section>
</template>

<script setup lang="ts">
const showPopup = ref(false);

const cards = [
    {
        title: 'Наши услуги',
        description: 'Наша компания управляет операционной деятельностью от приёма товара у поставщика и доставки покупателю до клиентской поддержки.',
        image: '/images/static/clipboard-with-checklist.png',
        big: true
    },
    {
        subtitle: 'Логистические услуги',
        button: {
            text: 'Узнать больше',
            callback: () => { }
        }
    },
    {
        subtitle: 'Услуги по работе с товаром',
        button: {
            text: 'Узнать больше',
            callback: () => { }
        }
    },
    {
        subtitle: 'Упаковка товара',
        button: {
            text: 'Узнать больше',
            callback: () => { }
        }
    },
    {
        subtitle: 'Доп.услуги при упаковке товара',
        button: {
            text: 'Узнать больше',
            callback: () => { }
        }
    },
    {
        subtitle: 'Доп.услуги',
        button: {
            text: 'Узнать больше',
            callback: () => { }
        }
    },
    {
        subtitle: 'Хранение товара',
        button: {
            text: 'Узнать больше',
            callback: () => { }
        }
    },
    {
        subtitle: 'Фулфилмент "под ключ"',
        button: {
            text: 'Узнать больше',
            callback: () => { }
        },
        big: true
    }
];

function onCardButtonClick(callback: () => any) {
    console.log('hello')
    callback();
    showPopup.value = true;
}
</script>

<style scoped lang="scss">
.main-page-services {
    @include container;

    &__list {
        display: flex;
        justify-content: space-between;
        flex-wrap: wrap;
        row-gap: rem(20px);

        &-item {
            @include flex-item-width(3, 20px);

            &:first-child {
                margin-top: rem(20px);

                .main-page-services__card {
                    height: rem(201px);

                    &-description {
                        width: 63%;
                    }
                }
            }

            &.big {
                width: 100%;
            }

        }
    }

    &__card {
        position: relative;

        display: flex;
        justify-content: space-between;

        padding: rem(24px) 36px;

        border-radius: rem($border-radius-medium);
        background-color: $fill-col-secondary;

        &-inner {}

        &-title {
            @include font-title;
            @include text-huge;

            margin-bottom: rem(20px);
        }

        &-subtitle {
            font-size: rem(24px);
            font-weight: $font-weight-medium;
        }

        &-description {
            @include text-big($font-weight-medium, $line-height-big);
        }

        &-details-button {
            margin-top: rem(52px);
        }

        &-image {
            position: absolute;
            right: 10%;
            top: 0;
            height: 100%;

            &-pic {
                @include object-contain-full;
            }
        }
    }
}
</style>