<template>
    <section class="main-page-consultation">

        <div class="main-page-consultation__inner">

            <form class="main-page-consultation__form">
                <h4 class="main-page-consultation__form-title">
                    Остались еще вопросы?
                </h4>

                <input class="main-page-consultation__form-control"
                    type="text"
                    placeholder="Ваше имя">
                <input class="main-page-consultation__form-control"
                    type="text"
                    placeholder="+7 (963)">
                <input class="main-page-consultation__form-control"
                    type="text"
                    placeholder="Ваш вопрос">

                <UiButton class="main-page-consultation__form-submit"
                    text="Отправить"
                    @click.prevent />

            </form>

            <div class="main-page-consultation__image">
                <img class="main-page-consultation__image-pic"
                    src="/images/static/truck-with-checkpoints.png"
                    alt="Картинка чатов">
            </div>
        </div>

    </section>
</template>

<style scoped lang="scss">
.main-page-consultation {

    background-color: $fill-col-secondary;

    height: 610px;

    &__inner {
        @include container;

        display: flex;
        justify-content: space-between;
    }

    &__image {
        width:55%;
        min-height: 100%;
        margin-left: rem(52px);

        &-pic {
            @include object-contain-full;
        }
    }

    &__form {
        display: flex;
        flex-direction: column;

        flex-shrink: 0;

        width: 45%;
        margin-top: rem(80px);

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