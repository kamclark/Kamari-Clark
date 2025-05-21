<template>
  <div class="employer-card">
    <h2>{{ employer.name }}</h2>
    <p><strong>Role:</strong> {{ employer.role }}</p>
    <p><strong>Location:</strong> {{ employer.location }}</p>
    <p><strong>Dates:</strong> {{ employer.dates }}</p>
    <p v-if="employer.description"><strong>Description:</strong> {{ employer.description }}</p>
    <a v-if="employer.website" :href="employer.website" target="_blank" rel="noopener">Company Website</a>
  </div>
</template>

<script setup>
defineProps({
  employer: {
    type: Object,
    required: true,
    default: () => ({
      name: '',
      role: '',
      location: '',
      dates: '',
      description: '',
      website: ''
    })
  }
});
</script>

<style scoped>
.employer-card {
  border: 1px solid #ddd;
  border-radius: 8px;
  padding: 1rem;
  margin-bottom: 1rem;
  background: #fafafa;
}
</style>
