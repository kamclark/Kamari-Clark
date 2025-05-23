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

<style scoped>
.site-header {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  width: 100%;
  background: var(--bg-header, #000); /* fallback to black if variable unset */
  z-index: 1000;
}

.site-header .container {
  display: flex;
  align-items: center;
  justify-content: space-between;
  max-width: 800px;
  margin: 0 auto;
  padding: 1rem 1.25rem;
}

.site-header h1 a {
  color: var(--accent-window);
  font-weight: bold;
}

.header-logo {
  height: 40px;
  width: auto;
}
</style>
