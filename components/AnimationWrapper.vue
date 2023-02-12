<template>
    <div class="animation-wrapper">
        <div class="animation-wrapper__top">&nbsp;</div>
        <div class="animation-wrapper__row">
            <div class="animation-wrapper__left">&nbsp;</div>
            <slot></slot>
            <div class="animation-wrapper__right">&nbsp;</div>
        </div>
        <div class="animation-wrapper__bottom">&nbsp;</div>
    </div>
</template>

<style lang="scss">
.animation-wrapper {

    &__top::before {
        transform: translateX(-100%);
    }

    &__bottom::before {
        transform: translateX(100%);
    }

    &__right::before {
        transform: translateY(-100%);
    }

    &__left::before {
        transform: translateY(100%);
    }


    &:hover {

        & .animation-wrapper__top::before,
        & .animation-wrapper__bottom::before,
        & .animation-wrapper__right::before,
        & .animation-wrapper__left::before {
            transform: translate(0);
        }
    }

    //Basics
    display: flex;
    flex-direction: column;

    &__row {
        display: flex;
        height: 100%;
    }

    &__top,
    &__bottom,
    &__right,
    &__left {
        position: relative;
        overflow: hidden;

        &::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            height: 100%;
            width: 100%;
            background-color: #ffa83d;
            transition: transform .3s ease-in;
        }
    }

    &__top,
    &__bottom {
        height: 5px;
        width: 100%;
    }

    &__right,
    &__left {
        height: 100%;
        width: 5px;
    }

    position: relative;
    z-index: 1;
}
</style>