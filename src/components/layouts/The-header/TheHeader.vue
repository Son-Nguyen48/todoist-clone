<template>
  <nav class="navbar navbar-expand-lg bg-header w-100 position-fixed">
    <div class="container-fluid">
      <left-header></left-header>
      <right-header></right-header>
    </div>
  </nav>
</template>

<script>
import LeftHeader from "./LeftHeader.vue";
import RightHeader from "./RightHeader.vue";

export default {
  components: { LeftHeader, RightHeader }
};
</script>

<style scoped>
.bg-header {
  background-color: #db4c3f;
}

nav {
  padding: 4px;
}
</style>
