<template>
  <div id="app">
    <div>
      <header class="position-sticky">
        <the-header></the-header>
      </header>

      <main class="d-flex">
        <sidebar-view></sidebar-view>
        <router-view class="main-content"></router-view>
      </main>
    </div>

    <!-- <the-modal></the-modal> -->
  </div>
</template>

<script>
import SidebarView from "./components/layouts/Sidebar-menu/SidebarView.vue";
import TheHeader from "./components/layouts/The-header/TheHeader.vue";
// import TheModal from "./components/layouts/The-main/The-modal/TheModal.vue";

export default {
  components: {
    TheHeader,
    SidebarView
    // TheModal
  }
};
</script>

<style scoped>
main {
  padding-top: 44px;
}

.main-content {
  padding-left: 305px;
}

header {
  z-index: 9999;
}
</style>
