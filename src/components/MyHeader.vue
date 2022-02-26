<template>
  <header>
      <div class="logo">
          <img src="../assets/img/Spotify_App_Logo.svg.png" alt="logo">
      </div>

      <select v-model="selectedGenre" @change="$emit('selectedGenreEvt', selectedGenre)">
          <option value="">Seleziona un genere</option>
          <option v-for="(genre, index) in genreCreate" :key="index" :value="genre">{{genre}}</option>
      </select>
  </header>
</template>

<script>
export default {
    name: 'MyHeader',
    props: {
        'genreCreate': Array,
    },
    data() {
        return {
            selectedGenre: '',
        }
    }
}
</script>

<style scoped lang="scss">
@import '../assets/style/variables.scss';
    header {
        height: 100px;
        display: flex;
        justify-content: space-between;
        align-items: center;
        background-color: $primaryColor;
        .logo {
            width: 50px;
            height: 50px;
            img {
                width: 100%;
            }
        }
    }
</style>