<template>
  <div class="project-card">
    <div class="card-header">
      <span class="project-title">{{ title }}</span>
      <a :href="github" class="external-link" target="_blank">GitHub</a>
    </div>
    <div class="card-body">
      <div class="project-info">
        <img :src="logo" alt="logo" class="logo"/>
        <p class="project-desc">{{ desc }}</p>
      <p class="quote">"{{ quote }}"</p>
        
      </div>
      <a :href="docs" class="doc-link" target="_blank">Documentation - README.md</a>
      <!-- <a :href="docs" class="doc-link" target="_blank">Link - Documentation</a> -->
      <div class="tags">
        <span v-for="tag in tags" :key="tag">{{ tag }}</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ProjectCard',
  props: {
    title: { type: String, required: true },
    github:{ type: String, required: true },
    logo:  { type: String, required: true },
    docs:  { type: String, required: true },
    desc:  { type: String, required: true },
    quote: { type: String, default: '' },
    tags:  { type: Array,  default: () => [] }
  }
}
</script>

<style scoped>
/* copy in your .project-card, .card-header, etc. rules here */
</style>
