<template>
    <section class="main-page-about">
        <div class="main-page-about__inner">

            <div class="main-page-about__info">
                <h2 class="main-page-about__info-title">
                    О нас
                </h2>
                <p class="main-page-about__info-paragraph">
                    Фулфилмент для маркетплейсов Order Care создан специалистами в сфере логистики и онлайн торговли с опытом работы в индустрии маркетплейсов с 2019 года.
                </p>
                <p class="main-page-about__info-paragraph">
                    Наша команда возьмет работу с торговыми площадками на себя под ключ: от подбора товара и доставки на склады маркетплейсов до полноценного маркетинга и продвижения товара в ТОП.
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
        flex-direction: row; // Default is row
        align-items: center; // Center items vertically in the container

        @media #{$screen-tablet} {
            flex-direction: column; // Stack elements vertically on smaller screens
        }
    }

    &__info {
        position: relative;
        z-index: 1;
        width: 100%; // Full width on mobile devices
        max-width: rem(958px); // Limit width on larger screens

        &-title {
            @include font-title;
            @include text-huge;
            text-align: center; // Center align the title on smaller screens
        }

        &-paragraph {
            @include text-big($font-weight-medium, $line-height-big);
            width: 100%; // Full width to utilize space
            max-width: rem(700px); // Limit width for readability
            margin-top: rem(20px);
            margin-left: auto; // Centering if needed
            margin-right: auto;
        }

        &-detail-button {
            margin-top: rem(40px);
            display: block; // Ensure the button is a block element to center
            margin-left: auto;
            margin-right: auto;
        }
    }

    &__image {
        position: absolute; // Adjust image positioning for mobile
        z-index: 0;
        right: 0;
        top: 0; // Adjust top on mobile to not overlap
        width: 100%; // Full width on mobile
        height: auto; // Maintain aspect ratio
        max-width: 50%; // Limit width on larger screens
        max-height: 100%;

        &-pic {
            width: 100%;
            height: auto; // Adjust height to maintain aspect ratio
        }

        @media #{$screen-tablet} {
            position: relative; // Relative positioning on smaller screens
            margin-top: rem(20px);
        }
    }
}
</style>