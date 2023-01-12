<script>
import CardList from './CardList.vue';
export default {
    name: 'AppMain',
    components: {
        CardList,
    },
    data() {
        return {
            typeOfArchetypes: ['Alien', 'Laval', 'Vylon', 'Inzektor', 'Umi', 'Gusto'],
            selectedModel: 'alien'
        }
    }
}
</script>
<template>
    <main class="py-5">
        <section id="chose-archetypes-cards" class="container">
            <select v-model="selectedModel" @change="$emit('sendChoseArchetype', selectedModel.toLowerCase())"
                name="archetypes" id="archetypes-select">
                <option v-for="singleArchetypeTxt in typeOfArchetypes" :value="singleArchetypeTxt.toLowerCase()">
                    {{singleArchetypeTxt}}
                </option>
            </select>
        </section>
        <section id="cards" class="container d-flex my-5 p-4 flex-column">

            <CardList />

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