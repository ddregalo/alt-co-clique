<template>
  <div>
    <b-navbar id="nav-bar" fixed="top">
      <b-navbar-brand href="/">
        <img src="../assets/acc.svg" 
          id="logo" 
          :class="{ 'title-hidden': !showTitle, 'title-show': showTitle }"/>
      </b-navbar-brand>

      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

      <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav>
          
        </b-navbar-nav>

        <!-- Right aligned nav items -->
        <b-navbar-nav class="ml-auto">
          <router-link :to="'contact'" id="last-nav-link">contact</router-link>
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  name: 'NavBar',
  data () {
    return {
      showTitle: false,
      lastScrollPosition: 0
    }
  },
  
  mounted () {
  window.addEventListener('scroll', this.onScroll)
  },
  beforeDestroy () {
    window.removeEventListener('scroll', this.onScroll)
  },
  methods: {
  onScroll () {
    // Get the current scroll position
    const currentScrollPosition = window.pageYOffset || document.documentElement.scrollTop
    // Because of momentum scrolling on mobiles, we shouldn't continue if it is less than zero
    if (currentScrollPosition < 0) {
      return
    }
    // Here we determine whether we need to show or hide the navbar
    this.showTitle = currentScrollPosition > this.lastScrollPosition
    // Set the current scroll position as the last scroll position
    this.lastScrollPosition = currentScrollPosition
  }
}
});
</script>

<style scoped lang="scss">
  .title-hidden {
    transform: translate3d(0, -150%, 0);
    transition: 0.5s all ease-in-out;
  }

  .title-show {
    transform: translate3d(0, 30%, 0);
    transition: 0.5s all ease-in-out;
  }
  
  #last-nav-link {
    margin-right: 10em;
    text-decoration: none;
    color: rgb(245, 245, 245);
    text-transform: uppercase;
    font-size: 1.1em;
    font-family: 'Ropa Sans', sans-serif;
  }

  #nav-bar {
    background: transparent;
  }

  #logo {
    margin-left: 4em;
    max-height: 4em;
  }
</style>
