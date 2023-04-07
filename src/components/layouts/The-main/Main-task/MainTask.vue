<template>
  <div class="px-5">
    <ul>
      <li v-for="(task, index) in tasks" :key="task.id" class="task-item">
        <task-item
          :data="task"
          :index="index"
          @toggle-edit-task-form="toggleEditTaskForm"
          @edit-task="editTask"
          @delete-task="deleteTask"
          @click.native="openModal(task)"
        ></task-item>
      </li>

      <li class="task-item__add">
        <form-add-task @add-task="addTask"></form-add-task>
      </li>
    </ul>

    <the-modal
      @close-modal="isModalOpen = !isModalOpen"
      v-if="isModalOpen"
      :currentModal="currentModal"
    ></the-modal>
  </div>
</template>

<script>
import TaskItem from "./TaskItem.vue";
import FormAddTask from "./FormAddTask.vue";
import TheModal from "../The-modal/TheModal.vue";
import { cloneDeep } from "lodash";

export default {
  data() {
    return {
      tasks: [
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
        },
        {
          id: 5,
          name: "Get up",
          description: "Get up of course!",
          status: "done",
          priority: 2,
          dueDate: "2022-04-08",
          isEditTaskFormOpen: false
        },
        {
          id: 6,
          name: "Get up",
          description: "Get up of course!",
          status: "done",
          priority: 1,
          dueDate: "2022-04-08",
          isEditTaskFormOpen: false
        },
        {
          id: 7,
          name: "Get up",
          description: "Get up of course!",
          status: "done",
          priority: 3,
          dueDate: "2022-04-08",
          isEditTaskFormOpen: false
        }
      ],
      isModalOpen: false,
      currentModal: {}
    };
  },
  components: {
    TaskItem,
    FormAddTask,
    TheModal
  },
  methods: {
    addTask(data) {
      data.id = this.tasks.length + 1;
      this.tasks.push(data);
    },

    toggleEditTaskForm(index) {
      this.tasks[index].isEditTaskFormOpen =
        !this.tasks[index].isEditTaskFormOpen;
    },

    editTask(data) {
      this.tasks = this.tasks.map((i) => (i.id === data.id ? data : i));
      console.log(this.tasks, "tasks");
    },

    deleteTask(data) {
      this.tasks.splice(data, 1);
    },

    openModal(data) {
      this.isModalOpen = !this.isModalOpen;
      this.currentModal = cloneDeep(data);
      console.log(this.currentModal, "current");
    }
  }
};
</script>

<style scoped>
ul {
  padding: 0;
  margin: 0;
}

.task-item {
  border-bottom: 1px solid #f0f0f0;
}
</style>
