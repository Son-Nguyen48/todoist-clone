<template>
  <div role="button">
    <div v-show="!data.isEditTaskFormOpen">
      <div class="d-flex gap-2 pt-2">
        <div class="task_checkbox">
          <span>
            <svg
              xmlns="http://www.w3.org/2000/svg"
              height="24"
              width="24"
              class="h-6 w-6"
              :class="priorityColor"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
              stroke-width="2"
              id="priority-1"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z"
              ></path>
            </svg>
          </span>
        </div>

        <div class="task_content w-100 position-relative">
          <div class="task_content--text">
            <div class="task_content--detail fs-6">{{ data.name }}</div>
            <div class="task_content--description fs-6">
              {{ data.description }}
            </div>
            <div class="task_content--description fs-6">{{ data.status }}</div>
          </div>

          <div class="task_content--tags d-flex flex-wrap align-items-center">
            <div class="ms-auto d-flex gap-2 align-items-center">
              <span class="fs-12">Mailbox</span>
              <span>
                <svg
                  width="12"
                  height="12"
                  viewBox="0 0 16 16"
                  class="project_icon project_icon_inbox mailbox-icon"
                >
                  <g fill="currentColor">
                    <path
                      d="M13.5 9.5V12a1.5 1.5 0 01-1.5 1.5H4A1.5 1.5 0 012.5 12V9.5h3.75a1.75 1.75 0 003.5 0h3.75z"
                      opacity="0.1"
                    ></path>
                    <path
                      d="M10.491 2a2 2 0 011.923 1.45l1.509 5.28a2 2 0 01.077.55V12a2 2 0 01-2 2H4a2 2 0 01-2-2V9.28a2 2 0 01.077-.55l1.509-5.28A2 2 0 015.509 2h4.982zm0 1H5.51a1 1 0 00-.962.725l-1.509 5.28A1 1 0 003 9.28V12a1 1 0 001 1h8a1 1 0 001-1V9.28a1 1 0 00-.038-.275l-1.51-5.28a1 1 0 00-.96-.725zM6.25 9a.5.5 0 01.5.5 1.25 1.25 0 002.5 0 .5.5 0 01.5-.5h1.75a.5.5 0 110 1h-1.306a2.25 2.25 0 01-4.388 0H4.5a.5.5 0 010-1z"
                    ></path>
                  </g>
                </svg>
              </span>
            </div>
          </div>

          <div
            class="position-absolute top-0 end-0 task_content--action d-none align-items-center ms-auto gap-2"
          >
            <button @click="toggleEditTaskForm(index)" class="action__edit">
              <span>
                <svg width="24" height="24">
                  <g fill="none" fill-rule="evenodd">
                    <path
                      fill="currentColor"
                      d="M9.5 19h10a.5.5 0 110 1h-10a.5.5 0 110-1z"
                    ></path>
                    <path
                      stroke="currentColor"
                      d="M4.42 16.03a1.5 1.5 0 00-.43.9l-.22 2.02a.5.5 0 00.55.55l2.02-.21a1.5 1.5 0 00.9-.44L18.7 7.4a1.5 1.5 0 000-2.12l-.7-.7a1.5 1.5 0 00-2.13 0L4.42 16.02z"
                    ></path>
                  </g>
                </svg>
              </span>
            </button>

            <button @click="deleteTask(index)" class="action__delete">
              <span>
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  width="24"
                  height="24"
                  aria-hidden="true"
                >
                  <g fill="none" fill-rule="evenodd">
                    <path d="M0 0h24v24H0z"></path>
                    <rect
                      width="14"
                      height="1"
                      x="5"
                      y="6"
                      fill="currentColor"
                      rx="0.5"
                    ></rect>
                    <path
                      fill="currentColor"
                      d="M10 9h1v8h-1V9zm3 0h1v8h-1V9z"
                    ></path>
                    <path
                      stroke="currentColor"
                      d="M17.5 6.5h-11V18A1.5 1.5 0 008 19.5h8a1.5 1.5 0 001.5-1.5V6.5zm-9 0h7V5A1.5 1.5 0 0014 3.5h-4A1.5 1.5 0 008.5 5v1.5z"
                    ></path>
                  </g>
                </svg>
              </span>
            </button>

            <router-link class="action__reply" to="/task/">
              <span>
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  width="24"
                  height="24"
                  data-svgs-path="sm1/comments.svg"
                >
                  <path
                    fill="currentColor"
                    fill-rule="nonzero"
                    d="M11.707 20.793A1 1 0 0 1 10 20.086V18H5a2 2 0 0 1-2-2V6a2 2 0 0 1 2-2h14a2 2 0 0 1 2 2v10a2 2 0 0 1-2 2h-4.5l-2.793 2.793zM11 20.086L14.086 17H19a1 1 0 0 0 1-1V6a1 1 0 0 0-1-1H5a1 1 0 0 0-1 1v10a1 1 0 0 0 1 1h6v3.086z"
                  ></path>
                </svg>
              </span>
            </router-link>

            <button class="action__more">
              <span class="action__more--icon">
                <svg width="15" height="3">
                  <path
                    d="M1.5 3a1.5 1.5 0 110-3 1.5 1.5 0 010 3zm6 0a1.5 1.5 0 110-3 1.5 1.5 0 010 3zm6 0a1.5 1.5 0 110-3 1.5 1.5 0 010 3z"
                    fill="currentColor"
                    fill-rule="evenodd"
                  ></path>
                </svg>
              </span>
            </button>
          </div>
        </div>
      </div>
    </div>

    <div v-show="data.isEditTaskFormOpen">
      <form class="border border-secondary-subtle rounded p-3 fs-6" action="#">
        <div>
          <input
            class="w-100 border-0"
            type="text"
            v-model="form.name"
            placeholder="Task Name"
            ref="taskName"
          />
        </div>

        <div class="mt-2">
          <input
            class="w-100 border-0"
            type="text"
            id="taskDescription"
            v-model="form.description"
            placeholder="Task Description"
          />
        </div>

        <div class="mt-2">
          <input
            class="w-100 border-0"
            type="text"
            id="taskStatus"
            v-model="form.status"
            placeholder="Task Status"
          />
        </div>

        <div class="mt-2">
          <input
            class="w-100 border-0"
            type="date"
            name="taskDuedate"
            id="taskDueDate"
            v-model="form.dueDate"
          />
        </div>

        <div class="mt-2 d-flex">
          <div>
            <select
              class="py-1 rounded"
              name="taskPriority"
              id="taskPriority"
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
              @click.prevent="toggleEditTaskForm(index)"
              class="border-0 p-2 rounded fs-12"
            >
              <span>Cancel</span>
            </button>

            <button
              class="edit-task__button border-0 p-2 rounded fs-12 text-white"
              :class="form.name.trim() ? 'add-task' : 'not-alowed'"
              @click.prevent="editTask"
            >
              <span>Edit task</span>
            </button>
          </div>
        </div>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    data: {
      type: Object,
      require: true
    },
    index: {
      type: Number,
      require: true
    }
  },
  data() {
    return {
      form: this.data ? this.data : {}
    };
  },
  computed: {
    priorityColor() {
      return {
        1: "text-danger",
        2: "text-warning",
        3: "text-primary",
        4: "text-danprimary-emphasisger"
      }[this.form.priority];
    }
  },

  methods: {
    toggleEditTaskForm(index) {
      this.$emit("toggle-edit-task-form", index);
      if (this.data.isEditTaskFormOpen) {
        this.$nextTick(() => {
          this.$refs.taskName.focus();
        });
      }
    },

    editTask() {
      this.form.isEditTaskFormOpen = false;
      console.log(this.form, "form");
      this.$emit("edit-task", this.form);
    },

    deleteTask(index) {
      this.$emit("delete-task", index);
    }
  }
};
</script>

<style scoped>
.task_content--description {
  opacity: 0.6;
}

.mailbox-icon {
  color: #74a3ea;
}

a {
  color: black;
  display: block;
  padding: 4px;
  border-radius: 8px;
}

a:hover {
  color: black;
}

button {
  margin: 0;
  padding: 4px;
  border: none;
  background-color: transparent;
  border-radius: 8px;
}

button:hover:not(.edit-task__button),
a:hover {
  background-color: #eeeeee;
}

.task-item:hover .task_content .task_content--action {
  display: flex !important;
}

.action__more--icon {
  display: block;
  height: 24px;
  width: 24px;
}

.fs-12 {
  font-size: 12px;
}

.not-alowed {
  cursor: not-allowed;
  background-color: #f1b7b2;
}

.add-task {
  background-color: #dd4b39;
}

input:focus {
  outline: none;
  border: none;
}

form:focus-within {
  border: 1px solid black !important;
}
</style>
