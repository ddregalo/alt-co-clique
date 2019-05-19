<template>
  <div>
    <b-navbar 
      id="nav-bar" 
      fixed="top"
      :class="{ 
        'title-hidden': !showTitle, 
        'title-show': showTitle,
        'nav-transparent': !isTransparent,
        'nav-opaque': isTransparent,
        }">
      <b-navbar-brand href="/">
        <img src="../assets/acc.svg" 
          id="logo" 
          :class="{ 'title-hidden': !showTitle, 'title-show': showTitle }"/>
      </b-navbar-brand>
      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
      <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav>
          <!-- Left aligned nav items -->
        </b-navbar-nav>
        <!-- Right aligned nav items -->
        <b-navbar-nav class="ml-auto">
          <router-link 
            :to="'contact'" 
            id="last-nav-link"
            :class="{ 'title-hidden': !showTitle, 'title-show': showTitle }">
              contact
          </router-link>
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
      lastScrollPosition: 0,
      isTransparent: true,
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
      const currentScrollPosition = window.pageYOffset || document.documentElement.scrollTop
      if (currentScrollPosition < 0) {
        return
      }
      this.showTitle = currentScrollPosition > this.lastScrollPosition
      this.lastScrollPosition = currentScrollPosition
    }
  }
});
</script>

<style scoped lang="scss">
  .title-hidden {
    transform: translate3d(0, -222%, 0);
    transition: 0.5s all ease-in-out;
  }

  .title-show {
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
    min-height: 6em;
  }

  .nav-opaque { 
    background: black;
  }
  
  .nav-tranparent {
    background: transparent;
  }

  #logo {
    margin-left: 4em;
    max-height: 4em;
  }
</style>
