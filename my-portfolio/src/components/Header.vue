<template>
  <header class="site-header">
    <div class="container">
      <h1><a href="#">{{ title }}</a></h1>
            <img src="/logo.png" alt="Logo" class="header-logo" />
    </div>
  </header>
</template>

<script>
export default {
  name: 'SiteHeader',
  props: {
    title: {
      type: String,
      default: 'KC'
    },
    logoURL: {
      type: String,
      default: ''
    }
  }
}
</script>

<style scoped>
</style>
