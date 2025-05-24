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
          For any professional inquiries, work inquests or just to say "hey.....", ping me
          at
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
/* =================== User Info Window =================== */
.user-info-window {
  width: 30rem;
  max-width: 350px;
  margin: var(--gutter) auto;
  background: var(--bg-window);
  border-radius: var(--radius);
  box-shadow: 0 0 0 1px rgba(0, 0, 0, 0.05), 8px 8px 0 var(--shadow-window);
  overflow: hidden;
}
.user-info-window-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background: var(--accent-window);
  color: #fff;
  padding: 0.5rem 0.75rem;
  font-weight: 600;
}
.user-info-window-controls .dot {
  display: inline-block;
  width: 0.7rem;
  height: 0.7rem;
  background: #111;
  border-radius: 70%;
  margin-left: 0.3rem;
}

.user-info-window-content {
  padding: var(--gutter);
}
.user-info-window-content ol {
  list-style: none;
  counter-reset: item;
}
.user-info-window-content li {
  counter-increment: item;
  margin-bottom: 0.75rem;
  position: relative;
  padding-left: 1.6rem;
}
.user-info-window-content li::before {
  content: counter(item) ".";
  position: absolute;
  left: 0;
  font-weight: bold;
  color: var(--accent-window);
}
</style>
