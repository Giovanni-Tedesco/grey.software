<template>
  <div class="project-card pl-4 p-2 mr-4 mb-4">
    <span
      :style="`background-color:${getStatusColor(project.status)}`"
      class="status ml-auto mb-2"
      v-b-tooltip.hover
      :title="project.status"
    ></span>

    <div class="flex align-items-center mb-4">
      <img class="logo justify-start" :src="project.logo" />
      <div class="ml-3">
        <h5 class="project-heading">{{ project.name }}</h5>
      </div>
    </div>

    <div class="description">
      <p>{{ project.desc }}</p>
    </div>

    <div class="calls-to-action d-flex mt-4">
      <b-button
        size="lg"
        class="g-btn mr-4"
        :href="project.repo"
        target="_blank"
      >
        <fa-icon class="mr-2" :icon="['fab', 'github']"></fa-icon>Hacktoberfest
        Issues
      </b-button>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    project: {
      name: String,
      desc: String,
      repo: String,
      logo: String,
      demo: String,
      trailer: String,
      status: String,
    },
  },
  methods: {
    getStatusColor: function(status) {
      switch (status) {
        case 'Live Alpha': {
          return 'Red'
        }
        case 'Live Beta': {
          return 'Yellow'
        }
      }
    },
  },
}
</script>

<style scoped>
.status {
  top: 12px;
  right: 12px;
  height: 28px;
  width: 28px;
  border-radius: 50%;
  position: relative;
  opacity: 0.69;
  transition: opacity 0.2s ease-out;
}

.status:hover {
  opacity: 1;
}

.project-card {
  width: 369px;
  height: 309px;
  border-radius: 12px;
  background: var(--bg);
  box-shadow: 12px 24px 72px -12px rgba(0, 0, 0, 0.25);
  display: flex;
  justify-content: flex-start;
  align-content: flex-start;
  flex-direction: column;
}

.logo {
  height: 72px;
}

.project-heading {
  font-size: 32px;
  line-height: 1.2;
  font-weight: 800;
}

.description {
  font-size: 18px;
  line-height: 1.2;
  height: 72px;
  width: 309px;
}
</style>
