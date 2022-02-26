<template>
  <div id="app">
    <MyHeader @selectedGenreEvt="setSelectedGenre" :genreCreate="genreCreate"/>
    <MyMain @genresList="setGenre" :selectedGenre="selectedGenere"/>
  </div>
</template>

<script>
import MyHeader from './components/MyHeader.vue'
import MyMain from './components/MyMain.vue'

export default {
  name: 'App',
  components: {
    MyHeader,
    MyMain
  },
  data() {
    return {
      genreCreate: [],
      selectedGenere: '',
    }
  },
  methods: {
    setGenre(genreListEvt) {
      this.genreCreate = genreListEvt;
    },
    setSelectedGenre(selectedGenreEvt) {
      this.selectedGenere = selectedGenreEvt;
    }
  }
}
</script>

<style lang="scss">
  @import './assets/style/general.scss';
</style>
