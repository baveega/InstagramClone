<template>
  <div id="app">
    <navbar v-if="!$route.meta.hideNavbar"></navbar>
    <main class="container main">
      <router-view />
    </main>
  </div>
</template>

<script>
import Navbar from './components/Navbar/Navbar';

export default {
  name: 'app',
  data: function() {
    return {
      user: null,
    };
  },
  components: {
    navbar: Navbar,
  },
};
</script>

<style lang="scss">
body {
  background-color: #F5F5F5;
}

.main {
  margin-top: 92px;
}
</style>
