<template>
    <main>
        <div class="container" v-if="!loading">
            <div class="row">
                <div v-for="element, index in arrayDisco" :key="index" 
                class="col-xs col-sm-6 col-md-4 col-lg-2">
                    <Disco :items="element" />
                </div>
            </div>
        </div>
        <Loading v-else />
    </main>
</template>

<script>
import Disco from './Disco.vue';
import axios from 'axios';
import Loading from './Loading.vue';

export default {
    name: "RaccoltaDischi",
    components: {
        Disco,
        Loading
    },
    data: function(){
        return{
            apiUrl:"https://flynn.boolean.careers/exercises/api/array/music",
            arrayDisco: [],
            loading: true
        }
    },
    created: function(){
        axios.
            get(this.apiUrl)
            .then((result)=>{
                //console.log(result.data.response);
                this.arrayDisco = result.data.response;
                console.log(this.arrayDisco);
                this.loading = false;
            });
    }
}
</script>

<style lang="scss" scoped>
@import '../style/general.scss';

main {
    width: 100%;
    min-height: calc(100vh - 80px);
    padding: 30px 0;
    background-color: $bgColor;
}
</style>