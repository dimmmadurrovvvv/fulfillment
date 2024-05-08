<template>
    <section class="main-page-slogan">
        <div class="main-page-slogan__inner">
            <div class="main-page-slogan__title">
                <h2 class="main-page-slogan__title-text">
                    С нами у вас не будет никаких расходов
                </h2>
            </div>

            <div class="main-page-slogan__image">
                <img class="main-page-slogan__image-pic"
                    src="/images/static/slogan-pic.png"
                    alt="Иллюстрация слогана">
            </div>
        </div>
    </section>
</template>


<style scoped lang="scss">
.main-page-slogan {
    position: relative;

    height: rem(616px);

    background-color: $fill-col-primary-muted;

    &__inner {
        @include container;

        display: flex;
        align-items: center;
        height: 100%;
    }

    &__title {
        max-width: 50%;
        &-text {
            @include font-title;
            @include text-huge;

            line-height: 1.4;
        }
    }

    &__image {
        position: absolute;
        z-index: 0;
        right: 0;
        height: 100%;
        width: 50%;

        &-pic {
            @include absolute-all-null;
            @include object-contain-full;
        }
    }
}
</style>