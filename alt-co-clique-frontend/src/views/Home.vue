<template>
  <div class="home">
    <NavBar msg="Welcome to Your Vue.js + TypeScript App"/>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import NavBar from '@/components/NavBar.vue'; // @ is an alias to /src

export default Vue.extend({
  name: 'home',
  components: {
    NavBar,
  },
});
</script>
