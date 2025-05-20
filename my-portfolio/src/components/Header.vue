<template>
  <header class="site-header">
    <div class="container">
      <h1><a href="#">{{ title }}</a></h1>
    </div>
  </header>
</template>

<script>
export default {
  name: 'SiteHeader',
  props: { title: { type: String, default: 'KC' } }
}
</script>

<style scoped>
/* header styles */
</style>
