<template>
  <div class="home">
    <div class="slide">
      <!-- <b-img src="http://www.luapstudios.co.uk/sites/default/files/artwork/KK47_karen_el_khazen_guns_water_tank_elle_luap.JPG" fluid alt="Responsive image" id="landing-image" class="mw-100"></b-img> -->
    </div>
    <div class="banner-title">
      <img src="../assets/white.svg" fluid alt="Responsive image"/>
    </div>
    <div class="home-content-overlay">
      Scroll Up and Down this page to see the parallax scrolling effect.
      This div is just here to enable scrolling.
      Tip: Try to remove the background-attachment property to remove the scrolling effect.
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  name: 'home',
  components: {
  },
});
</script>

<style lang="scss" scoped>
  .banner-title {
    position: absolute;
    top: 30%;
    left: 70%;
    transform: translate(-50%, -50%);
    font-size: 3em;
    font-family: 'Ropa Sans', sans-serif;
    color: rgb(240, 240, 240);
    font-weight: lighter;
    letter-spacing: 15px;
  }

  .home-content-overlay {
    height:1000px;
    background-color:black;
    font-size: 36px;
    color: white;
  }

  .slide {
    /* The image used */
    background-image: url("http://www.luapstudios.co.uk/sites/default/files/artwork/KK47_karen_el_khazen_guns_water_tank_elle_luap.JPG");
    min-height: 650px; 
    background-attachment: fixed;
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
  }
  
  #landing-image {
    height: 20%;
    width: 100%;
  }
</style>
