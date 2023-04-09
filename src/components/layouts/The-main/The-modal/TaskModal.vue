<template>
  <div class="w-50 h-75 bg-white border border-danger rounded-4">
    <nav
      class="navbar navbar-expand rounded-top-5 border-bottom border-light-subtle d-flex px-4"
    >
      <div>
        <router-link
          to="/mailbox"
          class="text-dark text-decoration-none d-flex gap-2 align-items-center"
        >
          <span>
            <svg
              width="16"
              height="16"
              viewBox="0 0 16 16"
              class="project_icon project_icon_inbox text-primary"
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

          <span class="fs-12">Mailbox</span>
        </router-link>
      </div>

      <div class="ms-auto d-flex align-items-center gap-2">
        <button class="nav__btn-control rounded border-0">
          <span>
            <svg
              width="14"
              height="8"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                fill-rule="evenodd"
                clip-rule="evenodd"
                d="M13.854 7.604a.5.5 0 01-.708 0L7 1.457.854 7.604a.5.5 0 01-.708-.707l6.5-6.5a.5.5 0 01.708 0l6.5 6.5a.5.5 0 010 .707z"
                fill="currentColor"
              ></path>
            </svg>
          </span>
        </button>

        <button class="nav__btn-control rounded border-0">
          <span>
            <svg
              width="24"
              height="24"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                fill-rule="evenodd"
                clip-rule="evenodd"
                d="M5.146 8.397a.5.5 0 01.708 0L12 14.543l6.146-6.146a.5.5 0 01.708.707l-6.5 6.5a.5.5 0 01-.708 0l-6.5-6.5a.5.5 0 010-.707z"
                fill="currentColor"
              ></path>
            </svg>
          </span>
        </button>

        <button class="nav__btn-control rounded border-0">
          <span>
            <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24">
              <g
                fill="none"
                stroke="currentColor"
                stroke-linecap="round"
                transform="translate(3 10)"
              >
                <circle cx="2" cy="2" r="2"></circle>
                <circle cx="9" cy="2" r="2"></circle>
                <circle cx="16" cy="2" r="2"></circle>
              </g>
            </svg>
          </span>
        </button>

        <button @click="closeModal" class="nav__btn-control rounded border-0">
          <span>
            <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24">
              <path
                fill="currentColor"
                d="M5.146 5.146a.5.5 0 0 1 .708 0L12 11.293l6.146-6.147a.5.5 0 0 1 .638-.057l.07.057a.5.5 0 0 1 0 .708L12.707 12l6.147 6.146a.5.5 0 0 1 .057.638l-.057.07a.5.5 0 0 1-.708 0L12 12.707l-6.146 6.147a.5.5 0 0 1-.638.057l-.07-.057a.5.5 0 0 1 0-.708L11.293 12 5.146 5.854a.5.5 0 0 1-.057-.638z"
              ></path>
            </svg>
          </span>
        </button>
      </div>
    </nav>

    <div class="d-flex task-modal__content">
      <div class="task-modal__content--detail me-auto p-2">
        <task-content :currentModal="currentModal"></task-content>
        <form-add-task></form-add-task>
      </div>

      <div
        class="w-260 border-start border-light-subtle rounded-bottom px-3 py-2 h-100 task-modal__aside-content"
      >
        <div class="mx-auto aside-content__item aside-content__project-field">
          <p>Project</p>
          <button
            class="w-100 d-flex border-0 rounded aside-content__item--button"
          >
            <div class="button-title d-flex gap-2">
              <span>
                <svg
                  width="16"
                  height="16"
                  viewBox="0 0 16 16"
                  class="project_icon project_icon_inbox"
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
              <span>Mailbox</span>
            </div>

            <div class="ms-auto d-none modifier-button">
              <span>
                <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24">
                  <path
                    stroke="currentColor"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    d="M16 10l-4 4-4-4"
                    fill="none"
                    fill-rule="evenodd"
                  ></path>
                </svg>
              </span>
            </div>
          </button>
        </div>

        <hr />

        <div class="mx-auto aside-content__item aside-content__duedate-field">
          <p>Due date</p>
          <button
            class="w-100 d-flex border-0 rounded aside-content__item--button"
          >
            <div class="button-title d-flex gap-2">
              <span>
                <svg
                  width="16"
                  height="16"
                  viewBox="0 0 16 16"
                  fill="none"
                  xmlns="http://www.w3.org/2000/svg"
                  class="task-due-date-button date_overdue"
                >
                  <path
                    fill-rule="evenodd"
                    clip-rule="evenodd"
                    d="M12 2H4a2 2 0 00-2 2v8a2 2 0 002 2h8a2 2 0 002-2V4a2 2 0 00-2-2zM3 4a1 1 0 011-1h8a1 1 0 011 1v8a1 1 0 01-1 1H4a1 1 0 01-1-1V4zm8.5 6.75a.75.75 0 11-1.5 0 .75.75 0 011.5 0zM4.5 5a.5.5 0 000 1h7a.5.5 0 000-1h-7z"
                    fill="currentColor"
                  ></path>
                </svg>
              </span>
              <span>5 Apr</span>
            </div>

            <div class="ms-auto d-none modifier-button">
              <svg
                xmlns="http://www.w3.org/2000/svg"
                width="24"
                height="24"
                viewBox="0 0 24 24"
                aria-hidden="true"
              >
                <path
                  d="M8.854 8.146L12 11.293l3.146-3.147a.502.502 0 01.708.708L12.707 12l3.147 3.146a.502.502 0 01-.708.708L12 12.707l-3.146 3.147a.502.502 0 01-.708-.708L11.293 12 8.146 8.854a.502.502 0 01.708-.708z"
                  fill="currentColor"
                  fill-rule="nonzero"
                ></path>
              </svg>
            </div>
          </button>
        </div>

        <hr />

        <div class="mx-auto aside-content__item aside-content__priority-field">
          <p>Priority</p>
          <button
            class="w-100 d-flex border-0 rounded aside-content__item--button"
          >
            <div class="button-title d-flex gap-2">
              <span>
                <svg
                  width="16"
                  height="16"
                  viewBox="0 0 16 16"
                  fill="none"
                  xmlns="http://www.w3.org/2000/svg"
                  class="Gw1i-E3"
                  data-icon-name="priority-icon"
                  data-priority="1"
                >
                  <path
                    fill-rule="evenodd"
                    clip-rule="evenodd"
                    d="M2.276 2.553A.5.5 0 002 3v10.5a.5.5 0 001 0V9.829c.585-.216 1.42-.329 2.5-.329.765 0 1.265.115 2.342.474 1.173.391 1.757.526 2.658.526 1.404 0 2.475-.178 3.224-.553A.5.5 0 0014 9.5V3a.5.5 0 00-.724-.447C12.692 2.845 11.763 3 10.5 3c-.765 0-1.265-.115-2.342-.474C6.985 2.135 6.401 2 5.5 2c-1.404 0-2.475.179-3.224.553z"
                    fill="currentColor"
                  ></path>
                </svg>
              </span>
              <span>P1</span>
            </div>

            <div class="ms-auto d-none modifier-button">
              <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24">
                <path
                  stroke="currentColor"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  d="M16 10l-4 4-4-4"
                  fill="none"
                  fill-rule="evenodd"
                ></path>
              </svg>
            </div>
          </button>
        </div>

        <hr />

        <div class="mx-auto aside-content__item aside-content__labels-field">
          <button
            class="w-100 d-flex border-0 rounded aside-content__item--button"
          >
            <div class="button-title d-flex gap-2">
              <span>Labels</span>
            </div>

            <div class="ms-auto d-none modifier-button">
              <svg
                width="24"
                height="24"
                viewBox="0 0 24 24"
                fill="none"
                xmlns="http://www.w3.org/2000/svg"
              >
                <path
                  fill-rule="evenodd"
                  clip-rule="evenodd"
                  d="M12 6a.462.462 0 00-.461.462v5.077H6.462a.462.462 0 100 .922h5.077v5.077a.461.461 0 10.922 0v-5.077h5.077a.461.461 0 100-.922h-5.077V6.462A.462.462 0 0012 6z"
                  fill="currentColor"
                ></path>
              </svg>
            </div>
          </button>
        </div>

        <hr />

        <div class="mx-auto aside-content__item aside-content__reminder-field">
          <button
            class="w-100 d-flex border-0 rounded aside-content__item--button"
          >
            <div class="button-title d-flex gap-2">
              <span>Reminder</span>
              <span class="d-inline-block px-1 bg-warning rounded"> Pro </span>
            </div>

            <div class="ms-auto d-none modifier-button">
              <svg
                width="24"
                height="24"
                viewBox="0 0 24 24"
                fill="none"
                xmlns="http://www.w3.org/2000/svg"
              >
                <path
                  fill="currentColor"
                  fill-rule="evenodd"
                  clip-rule="evenodd"
                  d="M15 6.995V9H9V6.995C9 5.895 9.9 5 11.01 5h1.988C14.102 5 15 5.897 15 6.995zM8 9V6.995A3.003 3.003 0 0111.01 4h1.988A3.002 3.002 0 0116 6.995V9h.994C18.102 9 19 9.887 19 11v6c0 1.105-.897 2-2.006 2H7.006A1.998 1.998 0 015 17v-6c0-1.105.897-2 2.006-2H8zm-2 2v6c0 .556.446 1 1.006 1h9.988c.557 0 1.006-.448 1.006-1v-6c0-.556-.446-1-1.006-1H7.006C6.449 10 6 10.448 6 11zm4 3a2 2 0 104 0 2 2 0 00-4 0zm2 1a1 1 0 100-2 1 1 0 000 2z"
                ></path>
              </svg>
            </div>
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import TaskContent from "@/components/UI/TaskContent.vue";
import FormAddTask from "../Main-task/FormAddTask.vue";

export default {
  props: {
    currentModal: {
      type: Object,
      require: true
    }
  },
  components: { TaskContent, FormAddTask },
  methods: {
    closeModal() {
      this.$emit("close-modal");
    }
  },
  mounted() {
    console.log(this.currentModal, "currentModal");
  }
};
</script>

<style lang="scss" scoped>
.nav__btn-control {
  background-color: transparent;
  width: 26px;
}

.nav__btn-control:hover {
  background-color: #fafafa;
}

.fs-12 {
  font-size: 12px;
}

.w-260 {
  width: 260px;
}

.task-modal__content {
  height: calc(100% - 45px);
}

.task-modal__content--detail {
  width: calc(100% - 260px);
}

.task-modal__aside-content {
  background-color: #fafafa;
  border-bottom-right-radius: 12px;
}

.aside-content__item--button {
  background-color: transparent;
  transition: 0.2s ease transform;

  &:hover {
    background-color: #eeeeee;

    & .modifier-button {
      display: inline !important;
    }
  }

  &:active {
    transform: scale(0.92);
  }
}

.button-title {
  height: 26px;
}

button {
  padding: 0;
  margin: 0;
}
</style>
