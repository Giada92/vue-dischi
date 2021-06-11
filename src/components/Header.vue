<template>
    <header class="d-flex justify-content-between px-3">
        <div>
            <img src="../assets/spotify.png" alt="Logo Spotify">
        </div>
        <div>
            <select v-model="genereSelezionato" @change="$emit('cambiaGenere', genereSelezionato)">
                <option value="" >Selezione un genere</option>
                <option 
                :value="genere"
                v-for="genere, index in generi" :key="index">
                    {{ genere }}
                </option>
            </select>

            <select class="mx-3" v-model="artistaSelezionato" @change="$emit('cambiaArtista', artistaSelezionato)">
                <option value="">Selezione per Artista</option>
                <option v-for="artista, index in artisti" :key="index" 
                :value="artista">
                    {{ artista }}
                </option>
            </select>
        </div>
    </header>
</template>

<script>
export default {
    name:"Header",
    data(){
        return{
            genereSelezionato: "",
            artistaSelezionato: ""
        }
    },
    props: {
        generi: Array,
        artisti: Array
    }
}
</script>

<style lang="scss" scoped>
@import '../style/general.scss';

header {
    height: 80px;
    line-height: 80px;
    background-color: $mainColor;

    img {
        width: 50px;
    }
}

</style>