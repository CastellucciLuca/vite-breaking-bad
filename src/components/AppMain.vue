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
        <section id="cards" class="container d-flex my-5 p-4 flex-column">
            <!-- CARD FOUND -->
            <div class="card-found py-3">
                <span class="fw-bold ps-4">Found {{store.yuGiOhCards.length}} cards</span>
            </div>
            <!-- GENERATED CARDS -->
            <div class="cards-container d-flex flex-wrap ">
                <!-- IMPORT CARDS -->
                <SingleCard v-for="cardItem in store.yuGiOhCards" :cardProperty="cardItem" />
            </div>
        </section>
    </main>
</template>
<style lang="scss" scoped>
@use '../styles/partials/variables' as *;
main {
    background-color: $background;
    section#cards {
        background-color: $white;
        div.card-found {
            background-color: black;
            color: white;
            margin: 1rem .5rem 0;
        }
    }
}
</style>