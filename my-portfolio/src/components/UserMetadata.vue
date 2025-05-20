<template>
  <div class="window">
    <header class="window-header">
      <span class="window-title">User Metadata</span>
      <div class="window-controls">
        <span class="dot" v-for="n in 3" :key="n"></span>
      </div>
    </header>
    <div class="window-content">
      <ol>
        <li><strong>Employer:</strong> {{ employer }}</li>
        <li><strong>Skills:</strong> {{ skills.join(', ') }}</li>
      </ol>
    </div>
  </div>
</template>

<script>
export default {
  name: 'UserMeta',
  props: {
    employer: { type: String, required: true },
    skills:   { type: Array,  required: true }
  }
}
</script>

<style scoped>
/* copy in your .window, .window-header, etc. rules here */
</style>
