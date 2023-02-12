<script lang="ts" setup>

type Props = {
    serverName: string,
    specslListItems: string[],
    sublists: string[][],
    powerSupply: string,
    imgSrc: string,
    sku: string,
    deliveryTime: number
}

const props = defineProps<Props>();
</script>

<template>
    <div class="card">
        <h5 class="card__header">
            <NuxtLink to="#">{{ props.serverName }}</NuxtLink>
        </h5>

        <div class="card__main">
            <div class="card__lists-container">
                <ul class="card__list">
                    <li v-for="item in props.specslListItems">{{ item }}</li>

                    <li>
                        <ul v-for="list in props.sublists" class="card__sublist">
                            <li v-for="item in list">{{ item }}</li>
                        </ul>
                    </li>

                </ul>
                <span class="card__list-span">
                    <img src="https://frontline.nextron.no/Content/Images/config-icons/Power_resource_blue.svg"
                        alt="Power supply">
                    {{ props.powerSupply }}
                </span>
            </div>
            <img class="card__image" :src="`${props.imgSrc}`" alt="Image of server">
        </div>

        <div class="card__footer">
            <span class="card__disclaimer">{{ props.sku }}</span>
            <span class="card__disclaimer">Expected delivery: {{ props.deliveryTime }} days</span>
        </div>

    </div>
</template>

<style lang="scss">
.card {
    position: relative;
    z-index: 1;

    display: flex;
    flex-direction: column;

    width: 100%;
    height: 100%;

    padding: 1.5rem 2.5rem;
    background-color: white;


    //Main elements
    &__header {
        margin-bottom: 1.5rem;
        text-align: center;

        a,
        a:link,
        a:visited {
            color: black;
            font-size: 1.6rem;
            font-weight: 600;
        }
    }

    &__main {
        margin-bottom: 1rem;
        display: flex;
        align-items: center;
        justify-content: space-between;
        flex-wrap: wrap;
        gap: 1rem;
    }

    &__lists-container {
        flex: 1;

        @media (min-width: $bp-xs) {
            min-width: 256px;
        }
    }

    &__image {
        flex: 1;
        width: 100%;
        height: auto;
        max-width: 256px;
        min-width: 200px;

        @media (min-width: $bp-xs) {
            min-width: 256px;
        }
    }

    &__footer {
        margin-top: auto;
        display: flex;
        justify-content: space-between;
        flex-wrap: wrap;
        gap: .3rem;

        @media (min-width: $bp-xs) {
            gap: 1rem;
        }
    }


    //Subelements
    &__list {
        list-style: none;

        & li {
            display: flex;
            margin-bottom: .5rem;

            &::before {
                content: '❯';
                font-size: 1.4rem;
                margin-right: .8rem;
            }

        }
    }

    &__sublist {
        list-style: none;
        display: flex;
        flex-wrap: wrap;

        & li {
            margin-bottom: 0;

            &::before {
                content: '';
                margin: 0;
            }

            &::after {
                content: ',';
                margin-right: .5rem;
            }
        }
    }

    &__list-span {
        display: flex;
        align-items: center;

        & img {
            width: auto;
            height: 1.6rem;
            margin-left: -5px;
            margin-right: 5px;
        }
    }

    &__disclaimer {
        color: #5a5a5a;
        font-size: 1.2rem;
    }
}
</style>