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
    max-width: 200px;
    height: 300px;
    /* box-shadow: 0 4px 2px 5px rgba(#FFFF, 0.15); */
    background-color: $mainColor;
    cursor: pointer;

    &:hover {
        animation: scale 2s linear infinite;
        border: 1px solid #1ED760;
    }

    img {
        width: 150px;
        height: 160px;
    }

    h4 {
        margin-bottom: 15px;
        font-size: 18px;
        text-transform: uppercase;
        text-align: center;
        color: $lightText;
    }

    p {
        margin: 0;
        color: #66635D;
    }
}

@keyframes scale {
    to { 
        transform: scale(1); 
    }
    from { 
        transform: scale(1.05); 
    }
}
</style>