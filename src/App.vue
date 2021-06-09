<template>
  <div id="app">
    <!-- Intestazione pagina -->
    <Header />
    <!-- /Intestazione pagina -->

    <!-- Main -->
    <RaccoltaDischi />
    <!-- /Main -->

  </div>
</template>

<script>
import Header from './components/Header.vue';
import RaccoltaDischi from './components/RaccoltaDischi.vue';

export default {
  name: 'App',
  components: {
    Header,
    RaccoltaDischi
  }
}
</script>

<style lang="scss">
@import './style/general.scss';
</style>
