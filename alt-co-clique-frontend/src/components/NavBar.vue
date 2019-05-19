<template>
  <div>
    <b-navbar toggleable="lg" id="nav-bar">
      <b-navbar-brand href="#" id="nav-logo">ALT-CO CLIQUE</b-navbar-brand>

      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

      <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav>
          <router-link :to="'about'" id="first-nav-link">contact</router-link>
        </b-navbar-nav>

        <!-- Right aligned nav items -->
        <b-navbar-nav class="ml-auto">
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  name: 'NavBar',
  props: {
    msg: String,
  },
});
</script>

<style scoped lang="scss">
  #first-nav-link {
    margin-left: 50px;
    text-decoration: none;
    color: rgb(126, 126, 126);
    text-transform: uppercase;
    font-size: 0.9em;
  }

  #nav-bar {
    background-color: rgb(243, 243, 243)
  }

  #nav-logo {
    margin-left: 4em;
  }
</style>
