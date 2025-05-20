<template>
  <footer class="site-footer">
    <div class="container footer-grid">
      <div>
        <h3>Contact</h3>
        <ul><li><a href="#">LinkedIn</a></li></ul>
      </div>
      <div>
        <h3>Projects</h3>
        <ul>
          <li><a v-for="proj in projects" :key="proj" href="#">{{ proj }}</a></li>
        </ul>
      </div>
    </div>
  </footer>
</template>


<script>
export default {
  name: 'SiteFooter',
  props: {
    projects: { type: Array, default: () => [] }
  }
}
</script>

<style scoped>
/* copy in your footer styles here */
</style>
