<script setup lang="ts">
import { computed } from "vue";

export interface Props {
  tag: string;
  width?: string;
}

const props = withDefaults(defineProps<Props>(), {
  tag: "p",
});

const styles = computed(() => {
  return {
    ...(props.width && { width: props.width })
  };
});
</script>

<template>
  <component :is="tag" :style="styles"></component>
</template>

<style scoped>
* {
  width: 155px;
  height: 10px;

  background: var(--color-skeleton);
  border-radius: 4px;
  margin: 16px auto;
}
</style>
