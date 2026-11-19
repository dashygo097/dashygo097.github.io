<script setup lang="ts">
import TechIcon from "./TechIcon.vue";

defineProps<{
  title: string;
  items: string[];
}>();
</script>

<template>
  <div class="tech-group">
    <h3>{{ title }}</h3>
    <ul class="tech-list" :aria-label="title">
      <li v-for="item in items" :key="item"><TechIcon :name="item" />{{ item }}</li>
    </ul>
  </div>
</template>

<style scoped>
.tech-group h3 {
  margin: 0 0 1rem;
  font-size: 1rem;
  font-weight: 500;
}
.tech-list {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
  padding: 0;
  margin: 0;
  list-style: none;
}
.tech-list li {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  padding: 0.4rem 0.75rem;
  border: 1px solid var(--border);
  border-radius: 0.6rem;
  background: var(--surface);
  color: var(--text-secondary);
  font-size: 0.875rem;
  line-height: 1.5;
}
</style>
