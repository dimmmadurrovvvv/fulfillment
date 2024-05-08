<template>
    <section class="main-page-about">
        <div class="main-page-about__inner">

            <div class="main-page-about__info">
                <h2 class="main-page-about__info-title">
                    О нас
                </h2>
                <p class="main-page-about__info-paragraph">
                    Фулфилмент для маркетплейсов Order Care создан специалистами в сфере логистики и онлайн торговли с опытом работы в индустрии маркетплейсов с 2015 года.
                </p>
                <p class="main-page-about__info-paragraph">
                    Наша команда возьмет работу с торговыми площадками на себя под ключ: от складской обработки товара и доставки на склады маркетплейсов до полноценного маркетинга и продвижения товара в ТОП.
                </p>
                <p class="main-page-about__info-paragraph">
                    Нашими клиентами являются и могут стать как начинающие предприниматели, так и крупные производственные компании или дистрибьютеры, заинтересованные в новых каналах продаж своей продукции.
                </p>

                <UiButton class="main-page-about__info-detail-button"
                    text="Подробнее" />
            </div>

            <div class="main-page-about__image">
                <img class="main-page-about__image-pic"
                    src="/images/static/cv-with-hands.png"
                    alt="Документ в руках">
            </div>
        </div>
    </section>
</template>

<style scoped lang="scss">
.main-page-about {
    position: relative;

    &__inner {
        @include container;

        display: flex;
    }

    &__info {
        position: relative;
        z-index: 1;
        
        width: rem(958px);

        &-title {
            @include font-title;
            @include text-huge;
        }

        &-paragraph {
            @include text-big($font-weight-medium, $line-height-big);
            width: rem(700px);
            margin-top: rem(20px);
        }

        &-detail-button {
            margin-top: rem(40px);
        }
    }

    &__image {
        position: absolute;
        z-index: 0;
        right: 0;

        width: 50%;
        height: 100%;

        &-pic {
            @include absolute-all-null;
            @include object-contain-full;
        }

    }
}
</style>