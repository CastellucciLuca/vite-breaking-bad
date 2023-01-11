<script>
export default {
    name: 'SingleCard',
    props: [
        'cardProperty',
    ]
}
</script>
<template>
    <article class="single-card">
        <img :src="cardProperty.card_images[0].image_url" :alt="cardProperty.name">
        <div class="info-card text-center">
            <h3 class="text-light fs-4 mb-3">{{cardProperty.name}}</h3>
            <span>{{cardProperty.archetype}}</span>
        </div>
    </article>
</template>
<style lang="scss" scoped>
@use '../styles/partials/variables' as *;

article.single-card {
    width: calc(100% / 5 - 1rem);
    background-color: $background;
    margin: 0rem .5rem 1rem;

    img {
        width: 100%;
    }
}
</style>