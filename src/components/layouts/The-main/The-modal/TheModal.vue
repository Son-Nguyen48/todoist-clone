<template>
  <div
    class="vw-100 vh-100 position-fixed top-0 end-0 bg-modal d-flex justify-content-center align-items-center"
  >
    <task-modal
      @close-modal="closeModal"
      :currentModal="currentModal"
    ></task-modal>
  </div>
</template>

<script>
import TaskModal from "./TaskModal.vue";

export default {
  props: {
    currentModal: {
      type: Object,
      require: true
    }
  },
  components: {
    TaskModal
  },
  mounted() {
    console.log(this.currentModal, "currentModal");
  },
  methods: {
    closeModal() {
      this.$emit("close-modal");
    }
  }
};
</script>

<style scoped>
.bg-modal {
  background: linear-gradient(to top, transparent, rgb(230, 221, 221));
}
</style>
