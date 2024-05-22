<script setup>
import { computed } from "vue";

const props = defineProps({
  detail: {
    type: String,
    default: "",
  },
  summary: {
    type: String,
    default: "",
  },
  page: {
    type: String,
    default: "",
  },
  title: {
    type: String,
    default: "",
  },
});

const summClass = computed(() => {
  if (props.page === "man") {
    return "flex justify-between items-center w-[243px] h-[37px] shadow mb-[22px] border-l-[5px] border-l-pink px-[11px] hover:cursor-pointer text-sm font-bold text-manPage uppercase leading-9";
  }
  return props.page;
});

const summAfter = computed(() => {
  return props.summary;
});
</script>

<template>
  <details :class="`${props.detail}`">
    <summary :class="[summAfter, summClass]">{{ props.title }}</summary>
    <slot></slot>
  </details>
</template>

<style scoped>
.drop {
  display: flex;
  align-items: center;
  font-size: 16px;
  letter-spacing: 1px;
  color: #fbed90;
  text-transform: uppercase;
  width: 100vw;
}
.s-summary::after {
  content: "\25BC";
  color: #fbed90;
  font-size: 16px;
  margin-left: 50px;
}
.detail[open] > .s-summary::after {
  content: " \25B2";
  color: #fbed90;
  margin-left: 50px;
}
</style>