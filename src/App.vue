<template>
  <div id="app" class="app-container">
    <!-- Side Menu -->
    <SideMenu ref="sideMenu" />

    <!-- App content -->
    <Header @toggleSideMenu="toggleSideMenu" />
    <MainBody />
    <BottomNav />
  </div>
</template>

<script>
import Header from './components/Header.vue';
import MainBody from './components/MainBody.vue';
import BottomNav from './components/BottomNav.vue';
import SideMenu from './components/SideMenu.vue';

export default {
  components: {
    Header,
    MainBody,
    BottomNav,
    SideMenu,
  },
  methods: {
    toggleSideMenu() {
      this.$refs.sideMenu.toggleMenu();
    },
  },
};
</script>

<style>
/* Reset margins and paddings */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html, body {
  height: 100%;
  width: 100%;
}

#app {
  height: 100%;
  width: 100%;
  overflow: hidden; /* Prevent body from scrolling */
}

/* Layout configuration */
.app-container {
  display: flex;
  flex-direction: column;
  height: 100%;
  max-width: 490px;
  margin: 0 auto;
  position: relative; /* Relative positioning for side menu */
  overflow: hidden; /* Prevents the side menu from being visible before opening */
}

/* Header z-index to stay on top */
header {
  z-index: 999;
  position: relative;
}
</style>
