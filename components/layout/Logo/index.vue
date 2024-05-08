<template>
    <div class="logo"
        :class="logoClasses">
        <NuxtLink class="logo__link"
            to="/">
            <img class="logo__image"
                src="/images/static/logo.png"
                alt="Логотип компании">
        </NuxtLink>
    </div>
</template>

<script setup lang="ts">
import type { PropType } from 'vue';

const props = defineProps({
    size: {
        type: String as PropType<'small' | 'big'>,
        required: false,
        default: 'small'
    }
});

const logoClasses = [props.size];

</script>

<style scoped lang="scss">
.logo {
    position: relative;

    &.small {
        width: rem(36px);
        height: rem(36px);
    }

    &.big {
        width: rem(155px);
        height: rem(155px);
    }

    border-radius: 50%;

    &__link {
        @include absolute-all-null;
    }

    &__img {
        @include object-contain-full;
    }
}
</style>