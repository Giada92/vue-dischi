<template>
    <div class="wrappre_disco d-flex flex-column justify-content-center align-items-center mt-4">
        <img class="img-fluid mb-2" :src="items.poster" :alt="items.title">
        <h4 class="fw-bold">{{items.title}}</h4>
        <p>{{items.author}}</p>
        <p>{{items.year}}</p>
    </div>
</template>

<script>
export default {
    name: "Disco",
    props: [ "items"]
}
</script>

<style lang="scss" scoped>
@import '../style/general.scss';

.wrappre_disco{
    padding: 10px;
    height: 335px;
    background-color: $mainColor;
    cursor: pointer;

    img {
        width: 150px;
        height: 160px;
    }

    h4 {
        margin-bottom: 15px;
        font-size: 16px;
        text-transform: uppercase;
        text-align: center;
        color: $lightText;
    }

    p {
        margin: 0;
        color: #66635D;
    }
}
</style>