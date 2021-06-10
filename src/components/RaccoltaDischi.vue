<template>
    <main>
        <div class="container" v-if="!loading">
            <div class="row">
                <div class="col-12 text-center">
                    <RicercaGenere @cambiaGenere="cambiaFunzione" />
                </div>
                <div v-for="element, index in filtraGrenere" :key="index" 
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
import RicercaGenere from './RicercaGenere.vue';
import axios from 'axios';
import Loading from './Loading.vue';

export default {
    name: "RaccoltaDischi",
    components: {
        Disco,
        RicercaGenere,
        Loading
    },
    data: function(){
        return{
            apiUrl:"https://flynn.boolean.careers/exercises/api/array/music",
            arrayDisco: [],
            loading: true,
            genere: ""
        }
    },
    computed: {
        filtraGrenere: function () {

            if(this.genere == "All"){
                return this.arrayDisco;
            }

            const newArray = this.arrayDisco.filter(
                (element)=>{
                    console.log(element.genre);
                    return element.genre === this.genere;
                },
                    
            );
            return newArray;
        }
    },
    methods:{
        cambiaFunzione: function(newSelected){
            //console.log(newSelected);
            //console.log(newSelected);
            this.genere = newSelected;
            console.log("Genere importato dal figlio", this.genere);
            console.log("tutti i dischi", this.arrayDisco);
            //this.arrayGeneri = newSelected;
            //console.log(this.arrayGeneri);
        }
    },
    created: function(){
        axios.
            get(this.apiUrl)
            .then((result)=>{
                //console.log(result.data.response);
                this.arrayDisco = result.data.response;
                //console.log(this.arrayDisco);
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