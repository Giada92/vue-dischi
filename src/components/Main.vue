<template>
  <main v-if="!loading" class="container">
      <div class="cards d-flex flex-wrap mt-3">
          <Disco 
            v-for="arrayDisco, index in filtraGenereArtista" :key="index"
            :item="arrayDisco"
            />
      </div>
  </main>
  <Loading v-else />
</template>

<script>
import Disco from './Disco.vue';
import Loading from './Loading.vue';

import axios from 'axios';

export default {
    name:"Main",
    props: {
        genereSelezionato: String,
        artistaSelezionato: String
    },
    data(){
        return{
            apiUrl: "https://flynn.boolean.careers/exercises/api/array/music",
            arrayDischi: [],
            arrayGeneri: [],
            arrayArtisti: [],
            loading: true
        }
    },
    computed:{
        filtraGenereArtista:function(){
            var newArray=[]
            if(this.genereSelezionato == "" && this.artistaSelezionato == ""){
                return this.arrayDischi
            } else if (this.genereSelezionato !== ""){
                 newArray = this.arrayDischi.filter(
                    (element)=> {
                        return element.genre == this.genereSelezionato;
                    }
                );
            }else if (this.artistaSelezionato !== ""){
                 newArray = this.arrayDischi.filter(
                    (element)=> {
                        return element.author == this.artistaSelezionato;
                    }
                );
            }
            return newArray
        }
    },
    components: {
        Disco,
        Loading
    },
    created(){
        axios.
            get(this.apiUrl)
                .then((result)=> {
                    this.arrayDischi  = result.data.response;
                    //console.log(this.arrayDischi);
                    setInterval(
                        ()=>{ 
                            this.loading = false;
                        }, 3000);

                    this.arrayDischi.forEach(
                        (element) => {
                            //console.log(element);
                            if(!this.arrayGeneri.includes(element.genre)){
                                this.arrayGeneri.push(element.genre);
                            }

                            if(!this.arrayArtisti.includes(element.author)){
                                this.arrayArtisti.push(element.author);
                            }
                        }
                    );

                    this.$emit('appArrayGeneri', this.arrayGeneri);
                    this.$emit('appArrayArtisti', this.arrayArtisti);
                })
    }
}
</script>

<style lang="scss" scoped>

</style>