<template>
  <div class="d-flex justify-content-center align-items-center gap-2">
    <button
      class="right-header__subscribe-button d-flex align-items-center rounded"
    >
      <div>
        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24">
          <g fill="none" fill-rule="evenodd">
            <path
              stroke="#FFD093"
              fill="#FFD093"
              stroke-linejoin="bevel"
              d="M8.2 18.6l3.8-2.3 3.8 2.3a.8.8 0 0 0 1-.9l-.9-4.2 3.3-2.8a.8.8 0 0 0-.4-1.3L14.4 9l-1.7-4a.8.8 0 0 0-1.4 0L9.6 9l-4.4.4a.8.8 0 0 0-.4 1.3l3.3 2.8-1 4.2a.8.8 0 0 0 1.1.9z"
            ></path>
          </g>
        </svg>
      </div>

      <span>Subscribe to Pro</span>
    </button>

    <button class="right-header__add-button bg-header rounded p-1">
      <div>
        <svg width="24" height="24" viewBox="0 0 24 24" class="filter-white">
          <g fill="none" fill-rule="evenodd" transform="translate(4 3)">
            <mask id="jd4FBg" fill="#fff">
              <path
                d="M9 8h7a.5.5 0 1 1 0 1H9v7a.5.5 0 1 1-1 0V9H1a.5.5 0 0 1 0-1h7V1a.5.5 0 0 1 1 0v7z"
              ></path>
            </mask>
            <g mask="url(#jd4FBg)">
              <path fill="currentColor" d="M-4-3h24v24H-4z"></path>
            </g>
          </g>
        </svg>
      </div>
    </button>

    <button
      class="right-header__progress-button bg-header rounded d-flex justfy-content-center p-1 gap-1"
    >
      <div>
        <svg
          viewBox="-2 -2 4 4"
          style="transform: rotate(-90deg); width: 24px; height: 24px"
          class="filter-white"
        >
          <circle
            cx="0"
            cy="0"
            r="1.4"
            fill="none"
            visibility="visible"
            stroke="currentColor"
            stroke-width="0.2"
          ></circle>
          <path
            fill="currentColor"
            d="M 1 0 A 1 1 0 0 1 -0.8090169943749473 0.5877852522924732 L 0 0"
          ></path>
        </svg>
      </div>

      <span>2/5</span>
    </button>

    <button class="right-header__help-button bg-header rounded p-1">
      <div>
        <svg
          xmlns="http://www.w3.org/2000/svg"
          width="24"
          height="24"
          viewBox="0 0 24 24"
          aria-hidden="true"
          class="filter-white"
        >
          <path
            d="M12 3a9 9 0 11-.001 18.001A9 9 0 0112 3zm0 1a8 8 0 100 16 8 8 0 000-16zm-.093 10.794c.47 0 .802.355.802.856 0 .495-.331.85-.802.85-.471 0-.808-.355-.808-.85 0-.501.337-.856.808-.856zm.128-7.294c1.465 0 2.465.954 2.465 2.213 0 .96-.47 1.639-1.215 2.11-.738.458-.948.8-.948 1.443v.397H11.32v-.562c-.006-.808.366-1.358 1.163-1.86.674-.433.936-.818.936-1.473 0-.758-.559-1.314-1.425-1.314-.878 0-1.436.544-1.5 1.418H9.5c.064-1.32.901-2.372 2.535-2.372z"
            fill="currentColor"
            fill-rule="nonzero"
          ></path>
        </svg>
      </div>
    </button>

    <button class="right-header__notification-button bg-header rounded p-1">
      <div>
        <svg
          xmlns="http://www.w3.org/2000/svg"
          width="24"
          height="24"
          viewBox="0 0 24 24"
        >
          <path
            d="M12 3a5.75 5.75 0 015.75 5.75c0 3.24.682 5.875 2.03 7.927A1.5 1.5 0 0118.525 19H14.5a2.5 2.5 0 01-5 0H5.475a1.501 1.501 0 01-1.254-2.323C5.568 14.625 6.25 11.989 6.25 8.75A5.75 5.75 0 0112 3zm1.5 16h-3a1.5 1.5 0 003 0zM12 4a4.75 4.75 0 00-4.75 4.75c0 3.423-.731 6.248-2.193 8.476a.5.5 0 00.418.774h13.05a.5.5 0 00.418-.774c-1.462-2.227-2.193-5.053-2.193-8.476A4.75 4.75 0 0012 4z"
            fill="currentColor"
            fill-rule="nonzero"
          ></path>
        </svg>
      </div>
    </button>

    <button
      class="right-header__notification-button bg-header rounded-circle p-1"
    >
      <div>
        <img
          src="https://dcff1xvirvpfp.cloudfront.net/96eeb3e0a84b4485b4d3a681dd6905bd_big.jpg"
          alt="user"
          class="d-block rounded-circle"
        />
      </div>
    </button>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
img {
  border: 0;
  vertical-align: middle;
  width: 28px;
  height: 28px;
}
.bg-header {
  background-color: #db4c3f;
}

button {
  border: none;
  padding: 0;
  color: white;
}

.right-header__subscribe-button {
  background-color: #e27065;
  font-size: 12px;
  padding: 1px 6px;
}

.right-header__subscribe-button:hover {
  background-color: #b9473c;
}

.filter-white {
  filter: brightness(0) invert(1);
}

.right-header__add-button:hover,
.right-header__progress-button:hover,
.right-header__help-button:hover,
.right-header__notification-button:hover {
  background-color: #e27065;
}
</style>
