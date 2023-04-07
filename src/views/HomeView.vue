<template>
  <div class="w-100">
    <main-header class="mw-800 w-100 m-auto"></main-header>
    <main-task class="mw-800 w-100 m-auto h-auto"></main-task>
  </div>
</template>

<script>
import MainHeader from "@/components/layouts/The-main/MainHeader.vue";
import MainTask from "@/components/layouts/The-main/Main-task/MainTask.vue";
// @ is an alias to /src

export default {
  name: "HomeView",
  components: { MainHeader, MainTask }
};
</script>

<style scoped>
.mw-800 {
  max-width: 800px;
}
</style>
