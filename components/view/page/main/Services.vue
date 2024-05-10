<template>
    <section id ="services" class="main-page-services">
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
                            @click="onCardButtonClick(card.button.callback, card.subtitle)" />
                    </div>

                    <div v-if="card.image"
                        class="main-page-services__card-image">
                        <img :src="card.image"
                             alt="Иллюстрация карточки"
                             class="main-page-services__card-image-pic">
                    </div>
                </div>
            </li>
        </ul>
        <LazyViewPopupBase v-model="showPopup"
            :title="popupTitle" />
    </section>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const showPopup = ref(false);
const popupTitle = ref('Логистические услуги');

const cards = [
    {
        title: 'Наши услуги',
        description: 'Наша компания управляет операционной деятельностью от приёма товара у поставщика и доставки покупателю до клиентской поддержки.',
        image: '/images/static/clipboard-with-checklist.png',
        big: true
    },
    {
        subtitle: 'Доставка товара из Китая',
        button: {
            text: 'Узнать больше',
            callback: () => { }
        }
    },
    {
        subtitle: 'Забор и доставка товара',
        button: {
            text: 'Узнать больше',
            callback: () => { }
        }
    },
    {
        subtitle: 'Обработка товара',
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
        },
        big: true
    },
    {
        subtitle: 'Фулфилмент "под ключ',
        button: {
            text: 'Узнать больше',
            callback: () => { }
        },
        big: true
    }
];

function onCardButtonClick(callback: () => any, title: string) {
    callback();
    popupTitle.value = title; // Обновляем заголовок модального окна
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

      @media (max-width:$container-width-laptop) {
        flex-direction: column;
      }

        &-item {
            @include flex-item-width(3, 20px);
          @media (max-width:$container-width-laptop) {
            width: 100%;
          }
            &:first-child {
                margin-top: rem(20px);

                .main-page-services__card {
                    height: rem(201px);
                  @media (max-width:$container-width-laptop) {
                    height: 100%;
                  }
                    &-description {
                        width: 63%;
                      @media (max-width:$container-width-laptop) {
                        width: 100%;
                      }
                      @media (max-width: $container-width-mobile-big) {
                       @include text-average;
                      }
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
      height: 100%;
        display: flex;
        justify-content: space-between;

        padding: rem(24px) 36px;

        border-radius: rem($border-radius-medium);
        background-color: $fill-col-secondary;

      @media (max-width:$container-width-laptop) {
        padding: rem(24px);

        .big & {
          flex-direction: column;
          gap: 40px;
        }
      }
        &-inner {
          @media (max-width:$container-width-laptop) {
            width: 100%;
          }
        }

        &-title {
            @include font-title;
            @include text-huge;

            margin-bottom: rem(20px);

          @media (max-width: $container-width-tablet) {
            @include text-great;
          }
          @media (max-width: $container-width-mobile-big) {
            @include text-big;
            text-align: center;
          }
        }

        &-subtitle {
            font-size: rem(24px);
            font-weight: $font-weight-medium;
          @media (max-width:$container-width-laptop) {
            text-align: center;
          }
          @media (max-width:$container-width-mobile-big) {
            text-align: left;
          }
        }

        &-description {
            @include text-big($font-weight-medium, $line-height-big);
        }

        &-details-button {
            margin-top: rem(52px);
          @media (max-width:$container-width-laptop) {
            width: 100%;
          }
        }

        &-image {
            position: absolute;
            right: 10%;
            top: 0;
            height: 100%;
          @media (max-width:$container-width-laptop) {
            position: relative;
            right: 0;
            margin-left: auto;
          }
          @media (max-width:$container-width-mobile-big) {
            margin: 0 auto;
          }
            &-pic {
                @include object-contain-full;
              @media (max-width:$container-width-laptop) {
                max-height: 195px;
              }
            }
        }
    }
}
</style>
