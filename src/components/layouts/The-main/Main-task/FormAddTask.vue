<template>
  <div class="my-3">
    <div v-show="!isAddTaskFormOpen">
      <div
        @click="toggleAddTaskForm"
        role="button"
        class="d-flex align-items-center gap-2"
      >
        <span class="d-flex align-items-center add-task__circle">
          <svg width="13" height="13" class="add-task__icon">
            <path
              d="M6 6V.5a.5.5 0 011 0V6h5.5a.5.5 0 110 1H7v5.5a.5.5 0 11-1 0V7H.5a.5.5 0 010-1H6z"
              fill="currentColor"
              fill-rule="evenodd"
            ></path>
          </svg>
        </span>

        <span class="add-task__text">Add task</span>
      </div>
    </div>

    <div v-show="isAddTaskFormOpen">
      <form class="border border-secondary-subtle rounded p-3 fs-6" action="#">
        <div>
          <input
            class="w-100 border-0"
            type="text"
            v-model.trim="form.name"
            placeholder="Task Name"
            ref="taskName"
          />
        </div>

        <div class="mt-2">
          <input
            class="w-100 border-0"
            type="text"
            v-model="form.description"
            placeholder="Task Description"
          />
        </div>

        <div class="mt-2">
          <input
            class="w-100 border-0"
            type="text"
            v-model="form.status"
            placeholder="Task Status"
          />
        </div>

        <div class="mt-2">
          <input
            class="w-100 border-0"
            type="date"
            name="taskDuedate"
            v-model="form.dueDate"
          />
        </div>

        <div class="mt-2 d-flex">
          <div>
            <select
              class="py-1 rounded"
              name="taskPriority"
              v-model="form.priority"
            >
              <option value="priority">Select Priority for your task</option>
              <option :value="1">Priority 1</option>
              <option :value="2">Priority 2</option>
              <option :value="3">Priority 3</option>
              <option :value="4">Priority 4</option>
            </select>
          </div>

          <div class="ms-auto d-flex gap-2">
            <button
              @click="toggleAddTaskForm"
              class="border-0 p-2 rounded fs-12"
            >
              <span>Cancel</span>
            </button>

            <button
              @click.prevent="addTask"
              class="border-0 p-2 rounded fs-12 text-white"
              :class="form.name ? 'add-task' : 'not-alowed'"
            >
              <span>Add task</span>
            </button>
          </div>
        </div>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      form: {
        priority: "priority",
        isEditTaskFormOpen: false
      },
      isAddTaskFormOpen: false
    };
  },
  methods: {
    toggleAddTaskForm() {
      this.isAddTaskFormOpen = !this.isAddTaskFormOpen;
      if (this.isAddTaskFormOpen) {
        this.$nextTick(() => {
          this.$refs.taskName.focus();
        });
      }
    },
    addTask() {
      this.$emit("add-task", this.form);
      this.form = { priority: "priority", isEditTaskFormOpen: false };
    }
  }
};
</script>

<style scoped>
.add-task__icon {
  color: #dd4b39;
}

.task-item__add:hover .add-task__text {
  color: #dd4b39;
}

.task-item__add:hover .add-task__icon {
  color: white;
}

.add-task__circle {
  border-radius: 50%;
  padding: 2px;
}

.task-item__add:hover .add-task__circle {
  background-color: #dd4b39;
}

input:focus {
  outline: none;
  border: none;
}

.fs-12 {
  font-size: 12px;
}

form:focus-within {
  border: 1px solid black !important;
}

.not-alowed {
  background-color: #f1b7b2;
  cursor: not-allowed;
}

.add-task {
  background-color: #dd4b39;
}
</style>
