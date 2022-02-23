<template>
  <header>
      <div class="logo">
          <img src="../assets/img/Spotify_App_Logo.svg.png" alt="logo">
      </div>
  </header>
</template>

<script>
export default {
    name: 'MyHeader'
}
</script>

<style scoped lang="scss">
@import '../assets/style/variables.scss';
    header {
        height: 100px;
        display: flex;
        justify-content: flex-start;
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