<template>
  <div class="grid">
    <div class="row p-0 m-0">
      <div class="col-12 col-md-4">
        <div class="text-center py-4">
          <span>Late</span>
          <span>7</span>
        </div>
        <ul>
          <li
            class="border border-light-subtle rounded mb-2"
            v-for="item in lateTasks"
            :key="item.id"
          >
            <task-content
              @open-modal="openModal"
              :currentModal="item"
            ></task-content>
          </li>
        </ul>
      </div>
      <div class="col-12 col-md-4">
        <div class="text-center py-4">
          <span>Apr 8.</span>
          <span>Today</span>
          <span>1</span>
        </div>

        <ul>
          <li
            class="border border-light-subtle rounded mb-2"
            v-for="item in todayTasks"
            :key="item.id"
          >
            <task-content
              @open-modal="openModal"
              :currentModal="item"
            ></task-content>
          </li>
        </ul>
      </div>
      <div class="col-12 col-md-4">
        <div class="text-center py-4">
          <span>Apr 9.</span>
          <span>Tomorrow</span>
          <span>1</span>
        </div>

        <ul>
          <li
            class="border border-light-subtle rounded mb-2"
            v-for="item in tomorrowTasks"
            :key="item.id"
          >
            <task-content
              @open-modal="openModal"
              :currentModal="item"
            ></task-content>
          </li>
        </ul>
      </div>
    </div>

    <the-modal
      @close-modal="isModalOpen = !isModalOpen"
      v-if="isModalOpen"
      :currentModal="currentModal"
    ></the-modal>
  </div>
</template>

<script>
import TaskContent from "./TaskContent.vue";
import TheModal from "../layouts/The-main/The-modal/TheModal.vue";
export default {
  components: {
    TaskContent,
    TheModal
  },
  data() {
    return {
      lateTasks: [
        {
          id: 1,
          name: "Get up",
          description: "Get up of course!",
          status: "done",
          priority: 1,
          dueDate: "2022-04-08",
          isEditTaskFormOpen: false
        },
        {
          id: 2,
          name: "Get up",
          description: "Get up of course!",
          status: "done",
          priority: 3,
          dueDate: "2022-04-08",
          isEditTaskFormOpen: false
        },
        {
          id: 3,
          name: "Get up",
          description: "Get up of course!",
          status: "done",
          priority: 2,
          dueDate: "2022-04-08",
          isEditTaskFormOpen: false
        },
        {
          id: 4,
          name: "Get up",
          description: "Get up of course!",
          status: "done",
          priority: 4,
          dueDate: "2022-04-08",
          isEditTaskFormOpen: false
        }
      ],
      todayTasks: [
        {
          id: 5,
          name: "Get up",
          description: "Get up of course!",
          status: "done",
          priority: 1,
          dueDate: "2022-04-08",
          isEditTaskFormOpen: false
        }
      ],
      tomorrowTasks: [
        {
          id: 6,
          name: "Get up",
          description: "Get up of course!",
          status: "done",
          priority: 1,
          dueDate: "2022-04-08",
          isEditTaskFormOpen: false
        }
      ],
      isModalOpen: false,
      currentModal: {}
    };
  },
  methods: {
    openModal(data) {
      this.currentModal = data;
      this.isModalOpen = !this.isModalOpen;
    }
  }
};
</script>

<style></style>
