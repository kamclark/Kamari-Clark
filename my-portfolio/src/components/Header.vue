<template>
  <header class="site-header">
    <div class="container">
      <h1>
        <a href="#">{{ title }}</a>
      </h1>
    </div>
  </header>
</template>

<script>
export default {
  name: "SiteHeader",
  props: {
    title: {
      type: String,
      default: "KC",
    },
    logoURL: {
      type: String,
      default: "vue.svg",
    },
  },
};
</script>

<style scoped></style>
