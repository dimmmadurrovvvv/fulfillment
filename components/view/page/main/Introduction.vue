<template>
    <section class="main-page-introduction">
        <div class="main-page-introduction__inner">

            <div class="main-page-introduction__info">
                <h1 class="main-page-introduction__info-title">
                    {{ title }}
                </h1>
                <p class="main-page-introduction__info-subtitle">
                    Доставим ваши товары от Китая до маркетплейса
                </p>
                <UiButton text="Стать клиентом"
                    class="main-page-introduction__info-submit" />
            </div>

            <div class="main-page-introduction__image">
                <img class="main-page-introduction__image-pic"
                    src="/images/static/marketplaces-with-truck.png"
                    alt="Иллюстрация грузовика">
            </div>

        </div>
    </section>
</template>

<script setup lang="ts">

const title = 'Order care - Ваш фулфилмент полного цикла\nв Москве'

</script>

<style scoped lang="scss">
.main-page-introduction {
    $height-desktop: 500px;

    height: rem($height-desktop);

    background-color: $fill-col-secondary;

    &__inner {
        @include container;

        display: flex;
    }

    &__info {
        margin-top: rem(100px);

        &-title {
            @include text-huge($font-weight-regular, $line-height-medium);
            @include font-title;

            white-space: pre-line;
        }

        &-subtitle {
            @include text-big($font-weight-medium);

            margin-top: rem(16px);
        }

        &-submit {
            margin-top: rem(86px);
        }
    }

    &__image {
        margin-top: rem(58px);
        margin-left: auto;

        width: 590px;

        &-pic {
            @include object-contain-full;
        }
    }
}
</style>