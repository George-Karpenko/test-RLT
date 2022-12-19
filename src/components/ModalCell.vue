<script setup lang="ts">
import BaseBoxs from "./BaseBoxs.vue";
import TextSkeleton from "./TextSkeleton.vue";
</script>

<template>
  <div class="modal__cell">
    <BaseBoxs class="modal__box" />
    <hr />
    <TextSkeleton tag="h2" />
    <TextSkeleton />
    <TextSkeleton />
    <TextSkeleton />
    <TextSkeleton width="180px" />
    <TextSkeleton width="80px" />
    <hr />
    <button>Удалить предмет</button>
  </div>
</template>

<style lang="scss">
.modal__cell {
  .modal__box {
    width: 130px;
    height: 130px;
    margin: 55px 60px 30px;
  }

  h2 {
    margin: 16px auto 24px;
    width: 211px;
    height: 30px;
    border-radius: 8px;
  }

  hr {
    margin: auto;
    margin-top: 24px;
    width: 220px;
    border: none;
    border-top: 1px solid #4d4d4d;
  }
  p {
    width: 211px;
  }

  button {
    margin: 18px 15px;
    width: calc(100% - 30px);
    height: 39px;
    background: #fa7272;
    border: none;
    border-radius: 8px;
    color: rgb(var(--color-text));
    font-family: "SF Pro Display";
    font-style: normal;
    font-weight: 400;
    font-size: 14px;
    line-height: 17px;
  }
}
</style>
