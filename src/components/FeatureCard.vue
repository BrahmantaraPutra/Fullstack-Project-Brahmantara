<script setup lang="ts">
interface Props {
  title: string;
  description: string;
  badge?: string;
}
const props = defineProps<Props>();
</script>

<template>
  <article class="feature-card">
    <div class="feature-card__header">
      <h3>{{ props.title }}</h3>
      <span v-if="props.badge" class="feature-card__badge">{{ props.badge }}</span>
    </div>
    <p>{{ props.description }}</p>
  </article>
</template>

<style scoped>
.feature-card {
  border: 1px solid rgba(203, 142, 102, 0.16);
  border-radius: 24px;
  padding: 28px;
  background: rgba(19, 26, 35, 0.92);
  transition:
    transform 0.25s ease,
    box-shadow 0.25s ease;
}
.feature-card:hover {
  transform: translateY(-3px);
  box-shadow: 0 24px 40px rgba(44, 49, 58, 0.28);
}
.feature-card__header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 1rem;
  margin-bottom: 0.8rem;
}
.feature-card__header h3 {
  margin: 0;
  font-size: 1.05rem;
  color: #efede9;
}
.feature-card__badge {
  background: rgba(203, 142, 102, 0.18);
  color: #131a23;
  padding: 0.4rem 0.75rem;
  border-radius: 9999px;
  font-size: 0.78rem;
  font-weight: 700;
}
.feature-card p {
  margin: 0;
  color: #d8d4cf;
  line-height: 1.75;
}
</style>
