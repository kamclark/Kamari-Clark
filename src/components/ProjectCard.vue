<template>
  <div class="project-card">
    <div class="card-header">
      <span class="project-title">{{ title }}</span>
      <a :href="github" class="external-link" target="_blank">GitHub</a>
    </div>
    <div class="card-body">
      <div class="project-info">
        <img :src="thumbnailURL" alt="project thumbnail" class="thumbnail" />
        <p class="project-desc">{{ desc }}</p>
        <p class="quote">"{{ quote }}"</p>
      </div>
      <a :href="docs" class="doc-link" target="_blank">Documentation - README.md</a>
      <div class="tags">
        <span v-for="tag in tags" :key="tag">{{ tag }}</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ProjectCard",
  props: {
    title: { type: String, required: true },
    github: { type: String, required: true },
    thumbnailURL: { type: String, required: true },
    docs: { type: String, required: true },
    desc: { type: String, required: true },
    quote: { type: String, default: "" },
    tags: { type: Array, default: () => [] },
  },
};
</script>

<style scoped>
/* =================== Project Cards =================== */
.project-card {
  /* max-width: 280px; */
  border-radius: var(--radius);
  overflow: hidden;
  background: var(--bg-window);
}
.card-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background: var(--accent-header);
  color: #fff;
  padding: 0.75rem 1rem;
}
.card-header .external-link {
  color: var(--link);
  font-weight: 500;
}
.card-body {
  padding: var(--gutter);
  color: #000000;
}
.project-info {
  display: flex;
  align-items: center;
  margin-bottom: var(--gutter);
}

.project-info .thumbnail {
  width: 15rem;
  height: 10rem;
  margin-right: var(--gutter);
  border-radius: 4px;
}
.project-info .doc-link {
  color: var(--tag-bg);
  margin-left: 0.5rem;
}
.project-desc {
  margin-bottom: 0.5rem;
  padding-right: 1rem;
}
.quote {
  color: var(--fg-muted);
  font-style: italic;
  margin-bottom: var(--gutter);
}
.tags {
  padding-top: 1rem;
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
}
.tags span {
  background: var(--tag-bg);
  color: var(--tag-fg);
  padding: 0.4rem 0.8rem;
  border-radius: 16px;
  font-size: 0.85rem;
}

@media (max-width: 600px) {
  .project-info {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    gap: var(--gutter);
  }

  .project-info .thumbnail {
    width: 100%;
    height: auto;
    margin: 0;
  }

  .project-desc {
    padding-right: 0;
    margin-bottom: 0.5rem;
  }
}
</style>
