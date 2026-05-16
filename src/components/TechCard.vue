<script setup lang="ts">
import { computed } from "vue";

interface Props {
  icon?: string;
  label: string;
  detail: string;
}
const props = defineProps<Props>();

const hasImage = computed(() => !!props.icon && props.icon.startsWith("http"));
</script>

<template>
  <div class="tech-card">
    <div v-if="props.icon" class="tech-card__icon">
      <img v-if="hasImage" :src="props.icon" :alt="props.label" />
      <span v-else>{{ props.icon }}</span>
    </div>
    <div class="tech-card__title">{{ props.label }}</div>
    <div class="tech-card__detail">{{ props.detail }}</div>
  </div>
</template>

<style scoped>
.tech-card {
  border: 1px solid rgba(203, 142, 102, 0.16);
  border-radius: 24px;
  padding: 24px;
  background: rgba(19, 26, 35, 0.92);
  transition:
    transform 0.25s ease,
    box-shadow 0.25s ease;
}
.tech-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 25px 45px rgba(44, 49, 58, 0.22);
}
.tech-card__icon {
  width: 48px;
  height: 48px;
  display: grid;
  place-items: center;
  border-radius: 16px;
  background: rgba(203, 142, 102, 0.18);
  margin-bottom: 1rem;
}
.tech-card__icon img {
  width: 28px;
  height: 28px;
  object-fit: contain;
}
.tech-card__icon span {
  font-size: 1.35rem;
}
.tech-card__title {
  font-weight: 700;
  font-size: 1rem;
  margin-bottom: 0.5rem;
  color: #efede9;
}
.tech-card__detail {
  font-size: 0.92rem;
  color: #d8d4cf;
  line-height: 1.7;
}
</style>
