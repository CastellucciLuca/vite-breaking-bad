<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
export default {
  components: {
    AppHeader,
    AppMain
  }
}
</script>

<template>
  <!-- IMPORT HEADER -->
  <AppHeader />
  <!-- IMPORT MAIN -->
  <AppMain />
</template>

<style lang="scss">
// STYLE+FRAMEWORKS
@use 'bootstrap/scss/bootstrap.scss' as *;
@use './styles/general.scss' as *;
@use './styles/partials/variables' as *;
</style>