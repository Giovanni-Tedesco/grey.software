<template>
  <div class="row">
    <div
      class="col-sm-6 col-lg-4 pr-sm-4 pr-lg-5 mt-5 mb-4"
      v-for="child in children"
      :key="child.title"
    >
      <ThreeColumnChild
        :title="child.title"
        :desc="child.desc"
        :icon="child.icon"
      />
    </div>
  </div>
</template>

<script>
export default {
  props: {
    children: Array,
  },
}
</script>
