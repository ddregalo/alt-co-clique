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
      <div id="nav-border">
      </div>
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
    if (document.getElementById("home-page")){
      window.addEventListener('scroll', this.onScroll);
    } else {
      this.showTitle = true;
    }
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
  .navbar {
    display: grid;
    grid-template-columns: 20% 80%;
    padding: 0;
    align-items: end;
  }
  
  .nav-opaque { 
    background: black;
  }
  
  .nav-tranparent {
    background: transparent;
  }
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
  
  #logo {
    margin-left: 4em;
    max-height: 4em;
  }

  #nav-bar {
    min-height: 6em;
  }

  #nav-border {
    height: 0.1em;
    width: 100%;
    grid-column-start: 1;
    grid-column-end: span col3-start;
    -webkit-animation-name: colorPulse;
    -webkit-animation-duration: 5s;
    -webkit-animation-iteration-count: 10;
    -webkit-animation-direction: alternate;
    -webkit-animation-timing-function: ease-in;
    -webkit-animation-fill-mode: forwards;
    -webkit-animation-delay: 2s;
  }

  @keyframes colorPulse {
      0% {background-color: rgb(75, 255, 231);}
     20% {background-color: rgb(230, 255, 92);}
    40% {background-color: rgb(255, 211, 90);}
    60% {background-color: rgb(255, 115, 236);}
    80% {background-color: rgb(151, 95, 255);}
    100% {background-color: rgb(47, 51, 255);}
}
</style>
