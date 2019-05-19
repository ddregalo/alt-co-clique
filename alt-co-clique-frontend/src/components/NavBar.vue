<template>
  <div>
    <b-navbar id="nav-bar" fixed="top">
      <b-navbar-brand href="/">
        <img src="../assets/white.svg" id="logo"/>
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
});
</script>

<style scoped lang="scss">
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
