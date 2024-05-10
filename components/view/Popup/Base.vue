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
                      text="Скачать прайс" />
                  <UiButton class="popup-base__footer-button"
                      text="Посмотреть прайс"
                      theme="transparent" />
              </div>
          </template>
      </ElDialog>
  </ClientOnly>
</template>

<script lang="ts" setup>
const props = defineProps({
    title: String,
    items: Array // Убедитесь, что принимаете items как prop
});
defineProps({
    title: {
        type: String,
        required: false,
        default: ''
    }
})

const dialogVisible = defineModel<boolean>();

const items = [
    { text: 'Забор товара с рынков Москвы: Южные ворота, Садовод, ТЯК', price: 'от 2 000 р' },
    { text: 'Забор товара по Москве и МО', price: 'от 2 000 р' },
    { text: 'Доставка товара объемом до 1 м3', price: 'от 2 000 р' },
    { text: 'Доставка товара объемом до 1 м3 до 2 м3', price: 'от 2 000 р' },
]
const dialogVisible = ref(true);
</script>

<style scoped lang="scss">
.popup-base {
    &__content {

        &-list {
            &-item {
                @include flex-space-between;
                gap: 20px;
                height: rem(95px);
              @media (max-width: $container-width-mobile-big) {
                height: 100%;
              }
              @media (max-width: $container-width-mobile-big) {
                flex-direction: column;
                gap: 10px;
                align-items: flex-start;
              }

                &:not(:first-child) {
                  @media (max-width: $container-width-mobile-big) {
                    padding-top: 10px;
                  }
                }
                  &:not(:last-child) {
                  @media (max-width: $container-width-mobile-big) {
                    padding-bottom: 10px;
                  }
                    border-bottom: 1px solid #B8B8B8;
                }

                &-text {
                    @include text-big;
                }

                &-price {
                  white-space: nowrap;
                    @include text-big($font-weight-semibold);
                }
            }
        }
    }

    &__footer {
        display: flex;
        align-items: flex-start;

        margin-top: rem(36px);

      @media (max-width: $container-width-tablet) {
        flex-direction: column;
        gap: 20px;
      }
        &-button {
          @media (max-width: $container-width-tablet) {
            width: 100%;
            margin: 0;
          }
            @include x-margin-items(22px);
        }
    }
}
</style>
