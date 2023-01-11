<script>
import { store } from '../store.js';
export default {
    name: 'AppMain',
    data() {
        return {
            store
        }
    }
}
</script>

<template>
    <main>
        <section id="cards">
            <article class="single-card" v-for="cardItem in store.yuGiOhCards">
                <img :src="cardItem.card_images[0].image_url" :alt="cardItem.name">
                <h3>{{cardItem.name}}</h3>
                <span>{{cardItem.archetype}}</span>
            </article>
        </section>
    </main>
</template>

<style lang="scss" scoped>
</style>