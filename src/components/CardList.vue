<script>
import { store } from '../store.js';
import AppLoader from './AppLoader.vue'
import SingleCard from './SingleCard.vue';
export default {
    name: 'CardList',
    components: { SingleCard, AppLoader },
    data() {
        return {
            store
        }
    }
}
</script>

<template >
    <div class="card-found py-3">
        <span class="fw-bold ps-4">Found {{ store.yuGiOhCards.length }} cards</span>
    </div>

    <!-- GENERATED CARDS -->
    <AppLoader v-if="store.yuGiOhCards.length === 0" class="m-auto" />

    <div v-else class="cards-container d-flex flex-wrap ">
        <!-- IMPORTED CARDS-->
        <SingleCard v-for="cardItem in store.yuGiOhCards" :cardProperty="cardItem" />
    </div>
</template>

<style lang="scss">
@use '../styles/partials/variables' as *;
div.card-found {
    background-color: black;
    color: white;
    margin: 1rem .5rem 0;
}
</style>