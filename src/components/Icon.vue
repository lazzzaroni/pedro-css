<template>
  <div :key="iconComponent">
    <component :class="`text-${color}`" :size="size" :is="iconComponent" />
  </div>
</template>

<script setup lang="ts">
import { defineAsyncComponent } from "vue";

const props = defineProps({
  icon: {
    type: String,
    default: "",
  },
  color: {
    type: String,
    default: "slate-50",
  },
  size: {
    type: Number,
    default: 20,
  },
});

const iconComponent = defineAsyncComponent(
  () => import(`./icons/${props.icon}.vue?component`)
);
</script>
