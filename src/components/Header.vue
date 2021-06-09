<template>
  <header class="container-fluid">
      <img src="../assets/spotify.png" alt="Logo spotify">
  </header>
</template>

<script>
export default {
    name: "Header"
}
</script>

<style lang="scss" scoped>
@import '../style/general.scss';

header {
    height: 80px;
    line-height: 80px;
    background-color: $mainColor;

    img {
        height: 80%;
        vertical-align: middle;
    }
}
</style>