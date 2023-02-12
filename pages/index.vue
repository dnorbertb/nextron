<script setup lang="ts">
import { useSeoMeta } from '#app';
import { servers } from '~~/data/data';

useSeoMeta({
    title: 'Cards'
})

</script>

<template>
    <div class="container">
        <Background />
        <main>
            <AnimationWrapper v-for="server in servers" :key="'card-' + server.name">
                <Card :server-name="server.name" :specsl-list-items="server.specslListItems" :sublists="server.sublists"
                    :power-supply="server.powerSupply" :img-src="server.imgSrc" :sku="server.sku"
                    :delivery-time="server.delivery" />
            </AnimationWrapper>
        </main>
    </div>
</template>

<style lang="scss">
.container {
    position: relative;
    min-height: 100vh;
    width: 100vw;
}

main {
    margin: 0 auto;
    max-width: 1280px;
    padding: 2rem;

    display: grid;
    gap: 2rem;

    @media (min-width: $bp-sm) {
        grid-template-columns: 1fr 1fr;
    }
}
</style>