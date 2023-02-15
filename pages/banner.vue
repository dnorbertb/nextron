<script setup lang="ts">
import { useSeoMeta } from '#app';

useSeoMeta({
    title: 'Banner'
})

</script>

<template>
    <div class="top">
        <h5>Building your <em>solutions</em></h5>
        <p>Customized servers, storage and workstations</p>
    </div>
    <div class="banner">
        <img src="/proc.png" alt="Processor image">
        <div class="texts">
            <h5>Design. Build. Accelerate. On The Ultimate Workstation Processor</h5>
            <p>Let AMD Ryzen™ Threadripper™ PRO processors be the productivity boosting engine at the heart of your next
                professional workstation.</p>
        </div>
    </div>
    <div class="footer">
        <p>Choose from our selection of solutions</p>
</div>
</template>

<style lang="scss" scoped>
.top,
.footer {
    text-align: center;
    color: white;
    background-color: #2d384c;
    position: relative;
    z-index: 2;
}

.top {
    & h5 {
        font-weight: 600;
        font-size: 2.2rem;
        padding: .5rem 0;

        & em {
            font-style: normal;
            color: #68afdb;
        }
    }

    & p {
        padding-bottom: .5rem;
    }
}



.banner {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 2rem;
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

.footer p {
    font-size: 1.8rem;
    padding: 1rem 0;
}
</style>