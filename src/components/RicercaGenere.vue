<template>
    <select name="Genere" v-model="selected" @change="$emit('cambiaGenere',selected)"
    class="form-select form-select-sm" aria-label=".form-select-sm">
    <option 
    v-for="option, index in options" :value="option.value" :key="index">
    {{ option.text}}
    </option>
        <!-- <option disabled value="">Ricerca per Genere</option>
        <option value="1">Rock</option>
        <option value="2">Pop</option>
        <option value="3">Jazz</option>
        <option value="4">Metal</option> -->
    </select>
</template>

<script>
export default {
    name: "RicercaGenere",
    data: function(){
        return {
            selected: "",
            options: [
            { 
                text: 'Tutti i Generi', 
                value: 'All' 
            },
            { 
                text: 'Rock', 
                value: 'Rock' 
            },
            { 
                text: 'Pop', 
                value: 'Pop' 
            },
            { 
                text: 'Jazz', 
                value: 'Jazz' },
            { 
                text: 'Metal',
                 value: 'Metal'
            }
            ]
        }
    }
}
</script>

<style lang="scss" scoped>

</style>