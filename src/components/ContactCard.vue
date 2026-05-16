<script setup lang="ts">
interface Props {
  label: string;
  value: string;
  href: string;
}
const props = defineProps<Props>();
</script>

<template>
  <a :href="props.href" class="contact-card" target="_blank" rel="noopener noreferrer">
    <span class="contact-card__label">{{ props.label }}</span>
    <span class="contact-card__value">{{ props.value }}</span>
  </a>
</template>

<style scoped>
.contact-card {
  display: grid;
  gap: 0.35rem;
  padding: 1.4rem 1.5rem;
  border-radius: 24px;
  border: 1px solid rgba(203, 142, 102, 0.16);
  background: rgba(19, 26, 35, 0.92);
  text-decoration: none;
  color: #efede9;
  transition:
    transform 0.25s ease,
    box-shadow 0.25s ease;
}
.contact-card:hover {
  transform: translateY(-3px);
  box-shadow: 0 22px 42px rgba(44, 49, 58, 0.2);
}
.contact-card__label {
  font-weight: 700;
  color: #efede9;
}
.contact-card__value {
  color: #a5a097;
}
</style>
