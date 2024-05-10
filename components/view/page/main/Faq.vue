<template>
    <section id="faq" class="main-page-faq">
        <ElCollapse class="main-page-faq__collapse">
            <ElCollapseItem class="main-page-faq__collapse-item"
                v-for="(item, idx) in items"
                :key="idx"
                :title="item.question"
                :name="item.question">
                <p class="main-page-faq__collapse-item-text">
                    {{ item.answer }}
                </p>
            </ElCollapseItem>
        </ElCollapse>
    </section>
</template>

<script lang="ts" setup>
const items = [
    {
        question: 'Как начать с вами сотрудничество?',
        answer: 'Свяжитесь с нами по телефону, указанному в шапке или через форму обратной свзяи на сайте'
    },
    {
        question: 'С каким минимальным количеством товара вы работаете?',
        answer: 'Мы работаем абсолютно с любым количеством товара.'
    },
    {
        question: 'С каким максимальным количеством товара вы работаете?',
        answer: 'Мы работаем абсолютно с любым количеством товара'
    },
]
</script>

<style scoped lang="scss">
.main-page-faq {
    @include container;

    &__collapse {
        &-item {
            @include y-margin-items(20px);
            &-text {
                @include text-big($font-weight-regular);

              @media (max-width: $container-width-tablet) {
                @include text-normal;
                font-weight: 400;
              }
                color: $txt-col-tetriary;
            }
        }
    }
}
</style>
