<template>
  <Navbar />
  <!-- <Dashboard /> -->
  <router-view></router-view>
</template>

<script>

import Navbar from './components/Navbar.vue';
// import Dashboard from './components/Dashboard.vue';
export default {
  components: {
    Navbar,
    // Dashboard,
  },
};
</script>