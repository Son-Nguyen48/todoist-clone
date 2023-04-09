<template>
  <div class="w-100">
    <main-header :name="'Shortly'" class="mw-800 w-100 m-auto"></main-header>
    <the-calendar></the-calendar>
    <board-view></board-view>
  </div>
</template>

<script>
import TheCalendar from "@/components/UI/TheCalendar.vue";
import BoardView from "@/components/UI/BoardView.vue";
import MainHeader from "@/components/layouts/The-main/MainHeader.vue";

export default {
  components: {
    MainHeader,
    TheCalendar,
    BoardView
  }
};
</script>

<style></style>
