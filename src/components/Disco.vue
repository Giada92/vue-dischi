<template>
    <div class="card mx-2 mb-3 p-3 text-center">
        <img class="mb-3" :src="item.poster" :alt="item.title">
        <h4 class="text-uppercase mb-3">{{ item.title }}</h4>
        <h5>{{ item.author }}</h5>
        <h5>{{ item.year }}</h5>
    </div>
</template>

<script>
export default {
    name: "Disco",
    props: {
        item : Object
    }
}
</script>

<style lang="scss" scoped>
@import '../style/general.scss';

.card {
    width: calc(100% / 5 - 30px);
    background-color: $mainColor;

    h4 {
        font-size: 18px;
        color: white;
    }

    h5 {
        font-size: 18px;
        color:gray;
    }
}
</style>