<template>
  <article class="kpi-card">
    <div class="kpi-label">{{ label }}</div>

    <div class="kpi-value" :class="{ compact: compactValue }">
      {{ value }}
      <small v-if="valueSuffix" class="kpi-suffix">{{ valueSuffix }}</small>
    </div>

    <div class="kpi-sub" :class="subtoneClass">{{ subtext }}</div>
  </article>
</template>

<script setup lang="ts">
import { computed } from 'vue';

interface Props {
  label: string;
  value: string | number;
  subtext: string;
  valueSuffix?: string;
  compactValue?: boolean;
  subtone?: 'default' | 'warn';
}

const props = withDefaults(defineProps<Props>(), {
  valueSuffix: '',
  compactValue: false,
  subtone: 'default',
});

const subtoneClass = computed(() => {
  return props.subtone === 'warn' ? 'warn' : 'default';
});
</script>

<style scoped>
.kpi-card {
  background: #fff;
  border: 1px solid #e5ece8;
  border-radius: 9px;
  min-height: 126px;
  padding: 18px 19px;
  position: relative;
  overflow: hidden;
  transition: transform 0.22s ease, box-shadow 0.22s ease, border-color 0.22s ease;
}

.kpi-card:hover {
  transform: translateY(-4px);
  border-color: #c8ddd3;
  box-shadow: 0 10px 22px rgba(26, 81, 69, 0.12);
}

.kpi-card::before {
  content: '';
  position: absolute;
  inset: auto -40px -40px auto;
  width: 120px;
  height: 120px;
  background: radial-gradient(circle, rgba(223, 242, 233, 0.5) 0%, rgba(223, 242, 233, 0) 68%);
  opacity: 0;
  transition: opacity 0.22s ease;
  pointer-events: none;
}

.kpi-card:hover::before {
  opacity: 1;
}

.kpi-label {
  color: #71847e;
  font-size: 12px;
  font-weight: 600;
}

.kpi-value {
  color: #12574b;
  font-family: 'Plus Jakarta Sans', sans-serif;
  font-size: 25px;
  font-weight: 700;
  margin: 11px 0 8px;
  line-height: 1.15;
}

.kpi-value.compact {
  font-size: 18px;
}

.kpi-suffix {
  color: #71847e;
  font-family: 'DM Sans', sans-serif;
  font-size: 12px;
  font-weight: 500;
  margin-left: 4px;
}

.kpi-sub {
  font-size: 12px;
}

.kpi-sub.default {
  color: #27836a;
}

.kpi-sub.warn {
  color: #d86d5e;
}
</style>
