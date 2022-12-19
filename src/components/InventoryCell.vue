<script setup lang="ts">
import BaseBoxs from "./BaseBoxs.vue";
</script>

<template>
  <div class="cell" data-item-counter="3">
    <BaseBoxs />
  </div>
</template>

<style scoped lang="scss">
.cell {
  position: relative;
  background: rgb(var(--color-background-soft));
  display: flex;
  justify-content: center;
  align-items: center;
}
.cell::before {
  content: attr(data-item-counter);
  position: absolute;
  bottom: -1px;
  right: 0;
  width: 16px;
  height: 16px;
  border: 1px solid #4d4d4d;
  border-radius: 6px 0px 0px 0px;
  font-family: "Inter";
  font-style: normal;
  font-weight: 500;
  font-size: 10px;
  line-height: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  color: rgba(var(--color-text), 0.4);
}
</style>
