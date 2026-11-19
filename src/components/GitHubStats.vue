<script setup lang="ts">
import { ref } from "vue";

defineProps<{ username: string }>();
const activityFailed = ref(false);
const languagesFailed = ref(false);
</script>

<template>
  <div class="stats-grid">
    <div class="stat-panel">
      <h3>GitHub activity</h3>
      <img
        v-if="!activityFailed"
        :src="`https://github-stats-extended.vercel.app/api?username=${encodeURIComponent(username)}&hide_title=true&hide_border=true&show_icons=true&include_all_commits=true&count_private=true&line_height=21&theme=github_dark&bg_color=15171c`"
        :alt="`GitHub activity statistics for ${username}`"
        loading="lazy"
        decoding="async"
        @error="activityFailed = true"
      />
      <p v-else role="status">
        Activity statistics are currently unavailable.
        <a :href="`https://github.com/${username}`">View GitHub profile</a>.
      </p>
    </div>
    <div class="stat-panel">
      <h3>Languages in commits</h3>
      <img
        v-if="!languagesFailed"
        :src="`https://github-profile-summary-cards.vercel.app/api/cards/most-commit-language?username=${encodeURIComponent(username)}&theme=github_dark`"
        :alt="`Most committed languages for ${username}`"
        loading="lazy"
        decoding="async"
        @error="languagesFailed = true"
      />
      <p v-else role="status">
        Language statistics are currently unavailable.
        <a :href="`https://github.com/${username}?tab=repositories`"
          >View repositories</a
        >.
      </p>
    </div>
  </div>
  <p class="stats-note">
    Statistics supplied by external services; availability and refresh times may
    vary.
  </p>
</template>

<style scoped>
.stats-grid {
  display: grid;
  grid-template-columns: 1.3fr 1fr;
  gap: 1rem;
}
.stat-panel {
  min-width: 0;
  padding: 1.25rem;
  border: 1px solid var(--border);
  border-radius: 1rem;
  background: var(--surface);
}
h3 {
  margin: 0 0 1rem;
  font-size: 1rem;
  font-weight: 500;
}
img {
  display: block;
  max-width: 100%;
  width: auto;
  height: auto;
  min-height: 10rem;
  margin: auto;
  object-fit: contain;
}
.stat-panel p {
  color: var(--text-secondary);
  font-size: 0.875rem;
}
.stats-note {
  margin: 1rem 0 0;
  color: var(--text-secondary);
  font-size: 0.8125rem;
}
@media (max-width: 640px) {
  .stats-grid {
    grid-template-columns: 1fr;
  }
}
</style>
