<template>
  <div class="w-75 h-75 bg-white border border-danger rounded-4">
    <nav
      class="navbar navbar-expand rounded-top-5 border-bottom border-light-subtle d-flex px-4"
    >
      <div>
        <router-link
          to="/mailbox"
          class="text-dark text-decoration-none d-flnav__btn-control ex align-"
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
        <button class="nav__btn-control border-0">
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

        <button class="nav__btn-control border-0">
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

        <button class="nav__btn-control border-0">
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

        <button class="nav__btn-control border-0">
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
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.nav__btn-control {
  background-color: transparent;
  width: 32px;
}

.nav__btn-control:hover {
  background-color: #fafafa;
}

.fs-12 {
  font-size: 12px;
}
</style>
