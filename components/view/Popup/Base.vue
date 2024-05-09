<template>
    <ClientOnly>
        <ElDialog class="popup-base"
                  v-model="dialogVisible"
                  :title="title">
            <div class="popup-base__content">
                <ul class="popup-base__content-list">
                    <li class="popup-base__content-list-item"
                        v-for="item in items"
                        :key="item.text">
                        <p class="popup-base__content-list-item-text">
                            {{ item.text }}
                        </p>
                        <span class="popup-base__content-list-item-price">
                            {{ item.price }}
                        </span>
                    </li>
                </ul>
            </div>
            <template #footer>
                <div class="popup-base__footer">
                    <UiButton class="popup-base__footer-button"
                              text="Скачать прайс"
                              @click="downloadPriceList"/>
                    <UiButton class="popup-base__footer-button"
                              text="Посмотреть прайс"
                              theme="transparent"
                              @click="viewPriceList"/>
                </div>
            </template>
        </ElDialog>
    </ClientOnly>
</template>

<script lang="ts" setup>
import { ref } from 'vue';

const dialogVisible = ref(false);

const items = [
    { text: 'Забор товара с рынков Москвы: Южные ворота, Садовод, ТЯК', price: 'от 2 000 р' },
    { text: 'Забор товара по Москве и МО', price: 'от 2 000 р' },
    { text: 'Доставка товара объемом до 1 м3', price: 'от 2 000 р' },
    { text: 'Доставка товара объемом до 1 м3 до 2 м3', price: 'от 2 000 р' },
]
const downloadPriceList = () => {
    const url = '/path/to/your/pricelist.pdf'; // Указать реальный путь
    const a = document.createElement('a');
    a.href = url;
    a.download = 'PriceList.pdf';
    document.body.appendChild(a);
    a.click();
    document.body.removeChild(a);
};

const viewPriceList = () => {
    const url = '/path/to/your/pricelist.pdf'; // Указать реальный путь
    window.open(url, '_blank');
};
</script>

<style scoped lang="scss">
.popup-base {
    &__content {

        &-list {
            &-item {
                @include flex-space-between;

                height: rem(95px);

                &:not(:last-child) {
                    border-bottom: 1px solid #B8B8B8;
                }

                &-text {
                    @include text-big;
                }

                &-price {
                    @include text-big($font-weight-semibold);
                }
            }
        }
    }

    &__footer {
        display: flex;
        align-items: flex-start;

        margin-top: rem(36px);

        &-button {
            @include x-margin-items(22px);
        }
    }
}
</style>