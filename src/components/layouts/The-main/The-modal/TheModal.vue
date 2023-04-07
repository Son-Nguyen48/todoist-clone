<template>
  <div
    class="vw-100 vh-100 position-absolute top-0 end-0 bg-modal d-flex justify-content-center align-items-center"
  >
    <task-modal></task-modal>
  </div>
</template>

<script>
import TaskModal from "./TaskModal.vue";

export default {
  components: {
    TaskModal
  }
};
</script>

<style scoped>
.bg-modal {
  background: linear-gradient(to top, transparent, rgb(230, 221, 221));
}
</style>
