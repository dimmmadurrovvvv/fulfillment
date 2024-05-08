<template>
    <section class="main-page-feedback">

        <div class="main-page-feedback__inner">

            <div class="main-page-feedback__image">
                <img class="main-page-feedback__image-pic"
                    src="/images/static/chat-clouds.png"
                    alt="Картинка чатов">
            </div>

            <form class="main-page-feedback__form">
                <h4 class="main-page-feedback__form-title">
                    Получите бесплатную консультацию
                </h4>

                <input class="main-page-feedback__form-control"
                    type="text"
                    placeholder="Ваше имя">
                <input class="main-page-feedback__form-control"
                    type="text"
                    placeholder="+7 (963)">
                <input class="main-page-feedback__form-control"
                    type="text"
                    placeholder="Ваш вопрос">

                <UiButton class="main-page-feedback__form-submit"
                    text="Отправить"
                    @click.prevent />

            </form>
        </div>

    </section>
</template>

<style scoped lang="scss">
.main-page-feedback {
    position: relative;

    height: 640px;

    &__inner {
        @include container;

        display: flex;
        justify-content: flex-end;
    }

    &__image {
        position: absolute;
        z-index: 0;
        left: 0;
        top: 0;
        height: 500px;
        width: 60%;

        &-pic {
            @include absolute-all-null;
            @include object-contain-full;
        }
    }

    &__form {
        position: relative;
        z-index: 1;

        display: flex;
        flex-direction: column;

        flex-shrink: 0;

        width: 40%;
        margin-top: rem(126px);

        &-title {
            @include font-title;
            @include text-huge;

            margin-bottom: rem(20px);
        }

        &-control {
            @include text-normal;

            height: rem(48px);
            margin-top: rem(50px);

            color: $txt-col-primary;
            border-bottom: 1px solid $border-col-tetriary;
            background-color: transparent;

            &:first-of-type {
                margin-top: 0;
            }

            &::placeholder {
                color: $txt-col-primary-muted-high;
            }
        }

        &-submit {
            width: fit-content;
            margin-top: rem(82px);
        }
    }
}
</style>