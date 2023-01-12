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
            selectModel: 'Alien'
        }
    },
    computed: {
        selectModelLowerCase() {
            return this.selectModel.toLowerCase()
        }
    }
}
</script>
<template>
    <main class="py-5">
        <section id="chose-archetypes-cards" class="container">
            <select v-model="selectModel" @change="$emit('sendChoseArchetype', selectModel)" name="archetypes"
                id="archetypes-select">
                <option v-for="singleArchetypeTxt in typeOfArchetypes" :value="singleArchetypeTxt">
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
    background-image: $background-image;
    background-repeat: no-repeat;
    background-size: cover;
    section#cards {
        background-color: $white;
    }
}
</style>