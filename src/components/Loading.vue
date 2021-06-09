<template>
    <div class="wrapper_loading d-flex flex-row justify-content-center align-items-center">
        <div class="text d-flex flex-row justify-content-center align-items-center">
            <span class="loader"></span>
            <p>Loading...</p>
        </div>
    </div>
</template>

<script>
export default {
    name: "Loading"
}
</script>

<style lang="scss" scoped>
@import '../style/general.scss';

.wrapper_loading {
    width: 100%;
    height: calc(100vh - 80px);

    .text {
        p{
            font-size: 20px;
            margin-left: 10px;
            margin-bottom: 0;
            text-transform: uppercase;
            color: $lightText;
        }
    }
}

.loader {
    display: inline-block;
    border: 8px solid $lightText;
    border-radius: 50%;
    border-top: 8px solid $mainColor;
    width: 50px;
    height: 50px;
    animation: spin 2s linear infinite;
}

@keyframes spin {
    to { 
        transform: rotate(0deg); 
    }
    from { 
        transform: rotate(360deg); 
    }
}


</style>