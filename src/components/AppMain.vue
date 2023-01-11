<script>
import { store } from '../store.js';
import SingleCard from './SingleCard.vue'
export default {
    name: 'AppMain',
    components: {
        SingleCard,
    },
    data() {
        return {
            store
        }
    }
}
</script>

<template>
    <main class="py-5">
        <section id="cards" class="container d-flex flex-wrap my-5 p-4">
            <!-- Import Cards -->
            <SingleCard v-for="cardItem in store.yuGiOhCards" :cardProperty="cardItem" />
        </section>
    </main>
</template>

<style lang="scss" scoped>
@use '../styles/partials/variables' as *;
main {
    background-color: $background;
    section#cards {
        background-color: $white;
    }
}
</style>