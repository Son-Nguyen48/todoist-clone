<template>
  <div>
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
          <div class="task_content--detail fs-6">{{ currentModal.name }}</div>
          <div class="task_content--description fs-6">
            {{ currentModal.description }}
          </div>
          <div class="task_content--description fs-6">
            {{ currentModal.status }}
          </div>
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

          <router-link class="action__reply" :to="`/task/:${currentModal.id}`">
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
</template>

<script>
export default {
  props: {
    currentModal: {
      type: Object,
      require: true
    }
  },
  computed: {
    priorityColor() {
      return {
        1: "text-danger",
        2: "text-warning",
        3: "text-primary",
        4: "text-danprimary-emphasisger"
      }[this.currentModal.priority];
    }
  },
  mounted() {
    console.log(this.priorityColor, "priorityColor");
  }
};
</script>

<style></style>
