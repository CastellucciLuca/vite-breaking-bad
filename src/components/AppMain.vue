<script>
import { store } from '../store.js';
import SingleCard from './SingleCard.vue'
import AppLoader from './AppLoader.vue'
export default {
    name: 'AppMain',
    components: {
        SingleCard,
        AppLoader
    },
    data() {
        return {
            store,
            loadCards: false
        }
    },
    methods: {
        isLoading() {
            setTimeout(() => {
                this.loadCards = true;
            }, 2000);
        }
    },
    created() {
        this.isLoading()
    }
}
</script>
<template>
    <main class="py-5">
        <section id="cards" class="container d-flex my-5 p-4 flex-column">
            <!-- CARD FOUND -->
            <div class="card-found py-3">
                <span v-if="!loadCards" class="fw-bold ps-4">Found ... cards</span>
                <span v-else class="fw-bold ps-4">Found {{ store.yuGiOhCards.length }} cards</span>
            </div>
            <!-- GENERATED CARDS -->
            <AppLoader v-if="(!loadCards) && (store.yuGiOhCards.length > 0)" class="m-auto" />
            <div v-else class="cards-container d-flex flex-wrap ">
                <!-- IMPORT CARD -->
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