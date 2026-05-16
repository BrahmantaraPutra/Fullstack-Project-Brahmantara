<script setup lang="ts">
interface Props {
  title: string;
  subtitle: string;
  description: string;
  tags: string[];
}
const props = defineProps<Props>();
</script>

<template>
  <article class="project-card">
    <div class="project-card__meta">
      <span class="project-card__label">Project</span>
      <span class="project-card__subtitle">{{ props.subtitle }}</span>
    </div>
    <h3>{{ props.title }}</h3>
    <p>{{ props.description }}</p>
    <div class="project-card__tags">
      <span v-for="tag in props.tags" :key="tag">{{ tag }}</span>
    </div>
    <a href="#contact" class="project-card__link">Lihat detail →</a>
  </article>
</template>

<style scoped>
.project-card {
  border: 1px solid rgba(203, 142, 102, 0.16);
  border-radius: 28px;
  padding: 26px;
  background: rgba(19, 26, 35, 0.92);
  display: flex;
  flex-direction: column;
  gap: 1rem;
  transition:
    transform 0.25s ease,
    box-shadow 0.25s ease;
}
.project-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 28px 48px rgba(44, 49, 58, 0.22);
}
.project-card__meta {
  display: flex;
  gap: 0.75rem;
  align-items: center;
  color: #a5a097;
  font-size: 0.88rem;
}
.project-card__label {
  background: rgba(203, 142, 102, 0.15);
  color: #efede9;
  padding: 0.35rem 0.65rem;
  border-radius: 9999px;
}
.project-card__subtitle {
  font-weight: 600;
  color: #efede9;
}
.project-card h3 {
  margin: 0;
  font-size: 1.2rem;
  color: #efede9;
}
.project-card p {
  margin: 0;
  color: #d8d4cf;
  line-height: 1.75;
}
.project-card__tags {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
}
.project-card__tags span {
  background: rgba(203, 142, 102, 0.15);
  color: #efede9;
  padding: 0.45rem 0.85rem;
  border-radius: 9999px;
  font-size: 0.82rem;
}
.project-card__link {
  color: #cb8e66;
  font-weight: 700;
  text-decoration: none;
}
</style>
