<template>
    <main>
        <div class="container">
            <div class="row">
                <div v-for="element, index in arrayDisco" :key="index" 
                class="col-xs-6 col-md-4 col-lg-2">
                    <Disco :items="element" />
                </div>
            </div>
        </div>
    </main>
</template>

<script>
import Disco from './Disco.vue';
import axios from 'axios';

export default {
    name: "RaccoltaDischi",
    components: {
        Disco
    },
    data: function(){
        return{
            apiUrl:"https://flynn.boolean.careers/exercises/api/array/music",
            arrayDisco: []
        }
    },
    created: function(){
        axios.
            get(this.apiUrl)
            .then((result)=>{
                //console.log(result.data.response);
                this.arrayDisco = result.data.response;
                console.log(this.arrayDisco);
            });
    }
}
</script>

<style lang="scss" scoped>
@import '../style/general.scss';

main {
    width: 100%;
    min-height: calc(100vh - 80px);
    background-color: $bgColor;
}
</style>