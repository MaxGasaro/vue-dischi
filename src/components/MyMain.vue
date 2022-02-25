<template>
  <main>
      <div class="container">
          <!--
          <div class="text-center">
              <input type="text" v-model="ricerca">
              <button>Ricerca</button>
          </div>
          -->
          <SearchComponent @seleziona="filtraGenere" :listaDischi="listaCanzoni"/>
          <div class="row row-cols-5 justify-content-center">
              <CardComponent v-for="(canzone, index) in listaGeneri" :key="index" :canzone="canzone">

              </CardComponent>
            <!--<div class="col-2" v-for="(canzone, index) in listaCanzoni" :key="index">
                <img :src="canzone.poster">
                <h2>{{canzone.title}}</h2>
                <div class="author">{{canzone.author}}</div>
                <div class="date">{{canzone.year}}</div>
            </div>-->

          </div>
      </div>
  </main>
</template>

<script>
import CardComponent from './partials/CardComponent.vue';
import SearchComponent from './partials/SearchComponent.vue';

const axios = require('axios');
export default {
    name: 'MyMain',
    data(){
        return {
            listaGeneri: [],
            ricerca: '',
            listaCanzoni: [],
            endpoint: 'https://flynn.boolean.careers/exercises/api/array/music'
        }
    },
    components: {
        CardComponent,
        SearchComponent
    },
    computed: {
        //filtraGenere() {
          //  return 
        //}
    },
    methods: {
        getMusic() {
            axios.get(this.endpoint)
            .then((response) => {
                this.listaCanzoni = response.data.response;
            }) 
        },
        filtraGenere() {
            this.listaGeneri = [];
            const valore = document.getElementById('ricercaGenere').value;
            this.listaCanzoni.forEach(element => {
                if(element.genre == valore) {
                    this.listaGeneri.push(element)
                } 
            })
        }
    },
    created() {
        this.getMusic();
    }
}
</script>

<style scoped lang="scss">
    @import '../assets/style/variables.scss';
    main {
        background-color: $mainColor;
        height: calc(100vh - 100px);
        padding: 20px;
        overflow: auto;
    }
</style>