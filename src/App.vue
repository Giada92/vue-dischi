<template>
  <div id="app">
    <!-- Intestazione pagina -->
    <Header :generi="allGeneri"
            @cambiaGenere="cambioSelezioneGenere"

            :artisti="allArtisti"
            @cambiaArtista="nuovoArtista"
     />
    <!-- /Intestazione pagina -->

    <!-- Main -->
    <Main @appArrayGeneri="funzioneGeneri"
          :genereSelezionato="nuovaSelezione"
          
          @appArrayArtisti="funzioneArtisti"
          :artistaSelezionato="nuovaSelezioneArtista"
     />
    <!-- /Main -->

  </div>
</template>

<script>
import Header from './components/Header.vue';
import Main from './components/Main.vue';


export default {
  name: 'App',
  data(){
    return{
      allGeneri:[],
      nuovaSelezione: "",
      allArtisti:[],
      nuovaSelezioneArtista:""
    }
  },
  methods:{
    funzioneGeneri:function(newArray){
      this.allGeneri = newArray;
    },
    cambioSelezioneGenere:function(select){
      this.nuovaSelezione = select;
    },
    funzioneArtisti:function(newArray){
      this.allArtisti = newArray;
    },
    nuovoArtista:function(string){
      this.nuovaSelezioneArtista = string;
      console.log(this.nuovaSelezioneArtista);
    }
  },
  components: {
    Header,
    Main
  }
}
</script>

<style lang="scss">
@import './style/general.scss';
</style>
