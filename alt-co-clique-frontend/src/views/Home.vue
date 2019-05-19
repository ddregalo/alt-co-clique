<template>
  <div class="home">
    <b-img src="http://www.luapstudios.co.uk/sites/default/files/artwork/KK47_karen_el_khazen_guns_water_tank_elle_luap.JPG" fluid alt="Responsive image" id="landing-image" class="mw-100"></b-img>
    <div class="banner-title">SITE COMING SOON</div>
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
    top: 40%;
    left: 50%;
    transform: translate(-50%, -50%);
    font-size: 3em;
    font-family: 'Ropa Sans', sans-serif;
    color: rgb(240, 240, 240);
    font-weight: lighter;
    letter-spacing: 15px;
  }
  
  #landing-image {
    height: 20%;
    width: 100%;
  }
</style>
