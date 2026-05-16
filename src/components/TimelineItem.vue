<script setup lang="ts">
import { computed } from "vue";

interface Props {
  year: string;
  title: string;
  subtitle: string;
  description: string;
  image?: string;
}
const props = defineProps<Props>();

const hasImage = computed(() => !!props.image && props.image.startsWith("http"));
</script>

<template>
  <div class="timeline-item">
    <div class="timeline-item__image">
      <img v-if="hasImage" :src="props.image" :alt="props.title" />
      <div v-else class="timeline-item__image-fallback">
        <span>Edu</span>
      </div>
    </div>
    <div class="timeline-item__content">
      <div class="timeline-item__header">
        <span class="timeline-item__year">{{ props.year }}</span>
        <h4>{{ props.title }}</h4>
      </div>
      <p class="timeline-item__subtitle">{{ props.subtitle }}</p>
      <p>{{ props.description }}</p>
    </div>
  </div>
</template>

<style scoped>
.timeline-item {
  display: grid;
  grid-template-columns: 180px 1fr;
  gap: 1.5rem;
  padding: 1.5rem;
  border-radius: 28px;
  background: rgba(19, 26, 35, 0.92);
  border: 1px solid rgba(203, 142, 102, 0.16);
  align-items: center;
  transition:
    transform 0.25s ease,
    box-shadow 0.25s ease;
}
.timeline-item:hover {
  transform: translateY(-4px);
  box-shadow: 0 24px 48px rgba(44, 49, 58, 0.22);
}
.timeline-item__image {
  width: 100%;
  min-height: 180px;
  border-radius: 26px;
  overflow: hidden;
  background: #624f45;
  display: grid;
  place-items: center;
}
.timeline-item__image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}
.timeline-item__image-fallback {
  width: 100%;
  height: 100%;
  display: grid;
  place-items: center;
  background: linear-gradient(180deg, #cb8e66 0%, #966d53 100%);
  color: #efede9;
  font-weight: 800;
  font-size: 1.5rem;
}
.timeline-item__content {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}
.timeline-item__header {
  display: flex;
  align-items: center;
  gap: 1rem;
  flex-wrap: wrap;
}
.timeline-item__year {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  min-width: 4.5rem;
  height: 2.8rem;
  padding: 0 1rem;
  border-radius: 18px;
  background: linear-gradient(180deg, #cb8e66 0%, #624f45 100%);
  color: #efede9;
  font-weight: 700;
}
.timeline-item h4 {
  margin: 0;
  font-size: 1.2rem;
  color: #efede9;
}
.timeline-item__subtitle {
  margin: 0;
  color: #a5a097;
  font-size: 0.95rem;
}
.timeline-item p:last-child {
  margin: 0;
  color: #d8d4cf;
  line-height: 1.75;
}
@media (max-width: 720px) {
  .timeline-item {
    grid-template-columns: 1fr;
  }
  .timeline-item__image {
    min-height: 200px;
  }
}
</style>
