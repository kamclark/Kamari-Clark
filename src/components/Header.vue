<template>
  <header class="site-header">
    <div class="header-container">
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
      default: "K.C",
    },
    logoURL: {
      type: String,
      default: "vue.svg",
    },
  },
};
</script>

<style scoped>

h1 a{
  color: white;
}

.site-header {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  width: 100%;
  background: var(--bg-header, #000); /* fallback to black if variable unset */
  z-index: 1000;
}

.site-header .header-container {
  display: flex;
  align-items: center;
  justify-content: space-between;
  max-width: 800px;
  margin: 0 auto;
  padding: 1rem 1.25rem;
}
</style>
