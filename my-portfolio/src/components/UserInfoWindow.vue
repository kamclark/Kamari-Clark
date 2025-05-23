<template>
  <div class="user-info-window">
    <header class="user-info-window-header">
      <span class="user-info-window-title">User Metadata</span>
      <div class="user-info-window-controls">
        <span class="dot" v-for="n in 3" :key="n"></span>
      </div>
    </header>
    <div class="user-info-window-content">
      <ol>
        <li><strong>Employer:</strong> {{ currentEmployer }}</li>
        <li><strong>Skills:</strong> [{{ skills.join(", ") }}]</li>
        <li>
        <strong>Contact:</strong>
          For any professional inquiries, work inquests or just to say "hey.....", ping me at
          <a href="mailto:kamnmclark@gmail.com">kamnmclark@gmail.com</a>.
        </li>
      </ol>
    </div>
  </div>
</template>

<script>
export default {
  name: "UserMeta",
  props: {
    currentEmployer: { type: String, required: true },
    skills: { type: Array, required: true },
  },
};
</script>

<style scoped>
/* copy in your .window, .window-header, etc. rules here */
</style>
