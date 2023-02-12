<script setup lang="ts">
import { useSeoMeta } from '#app';

useSeoMeta({
    title: 'Banner'
})

</script>

<template>
    <div class="banner">
        <!-- some background-image here -->
        <img src="/proc.png" alt="Processor image">
        <div class="texts">
            <h5>Design. Build. Accelerate. On The Ultimate Workstation Processor</h5>
            <p>Let AMD Ryzen™ Threadripper™ PRO processors be the productivity boosting engine at the heart of your next
                professional workstation.</p>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.banner {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 2rem;
    padding: 4rem;
    background-image: linear-gradient(to right, #815d19, #e99b0c 30%, #815d19);

    @media (min-width: $bp-sm) {
        gap: 6rem;
    }


    & img {
        height: 10rem;
        width: auto;
        filter: drop-shadow(0 0 3rem #ffdc16);

        @media (min-width: $bp-sm) {
            height: 30rem;
        }

    }

    & .texts {
        max-width: 80rem;
        color: white;

        & h5 {
            font-size: 1.6rem;
            font-weight: 600;
            margin-bottom: 1rem;

            @media (min-width: $bp-sm) {
                font-size: 2.2rem;
            }
        }

        & p {
            font-size: 1.2rem;
            font-weight: 300;

            @media (min-width: $bp-sm) {
                font-size: 1.6rem;
            }
        }
    }
}
</style>