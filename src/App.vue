<script>
import { store } from './store.js';
import axios from 'axios';
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
export default {
  components: {
    AppHeader,
    AppMain
  },
  data() {
    return {
      store,
      apiUrl: 'https://db.ygoprodeck.com/api/v7/cardinfo.php?',
      archetypeSelected: 'alien'
    }
  },
  methods: {
    getApiElement(archetypeChose) {
      this.store.yuGiOhCards = []
      axios.get(this.apiUrl, {
        params: {
          archetype: archetypeChose,
          num: 15,
          offset: 0
        }
      })
        .then((response) => {
          console.log(response.data.data);
          this.store.yuGiOhCards = response.data.data
        })
        .catch((error) => {
          console.log(error);
        });
    }
  },
  created() {
    this.getApiElement(this.archetypeSelected)
  },
}
</script>

<template>
  <!-- IMPORT HEADER -->
  <AppHeader />
  <!-- IMPORT MAIN -->
  <AppMain @sendChoseArchetype="getApiElement" />
</template>

<style lang="scss">
@use 'bootstrap/scss/bootstrap.scss' as *;
@use './styles/general.scss' as *;
@use './styles/partials/variables' as *;
</style>