<template>
    <div class="text-center">
        <select name="selectGenre" id="ricercaGenere" @change="filtraMusica">
            <option v-for="(disco,index) in listaDischi" :key="index" 
                    :value="disco.genre">{{disco.genre}}</option>
            <!--
            <option value="Pop">Pop</option>
            <option value="Jazz">Jazz</option>
            <option value="Metal">Metal</option>
            -->
        </select>
    </div>
</template>

<script>
export default {
    name: 'SearchComponent',
    props: {
        'listaDischi': Array
    },
    methods: {
        filtraMusica() {
            this.$emit('seleziona')
        }
    }
}
</script>

<style scoped lang="scss">

</style>