<template>
  <div id="app">
    <!-- Intestazione pagina -->
    <Header />
    <!-- /Intestazione pagina -->

    <!-- Main -->
    <!-- /Main -->

  </div>
</template>

<script>
import Header from './components/Header.vue';

export default {
  name: 'App',
  components: {
    Header,
  }
}
</script>

<style lang="scss">
@import './style/general.scss';
</style>
