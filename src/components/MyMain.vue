<template>
  <main>
      <div class="container">
          <div class="row justify-content-center">
              <CardComponent v-for="(canzone, index) in listaCanzoni" :key="index" :canzone="canzone">

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
const axios = require('axios');
export default {
    name: 'MyMain',
    data(){
        return {
            listaCanzoni: [],
            endpoint: 'https://flynn.boolean.careers/exercises/api/array/music'
        }
    },
    components: {
        CardComponent
    },
    methods: {
        getMusic() {
            axios.get(this.endpoint)
            .then((response) => {
                this.listaCanzoni = response.data.response;
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
    }
</style>