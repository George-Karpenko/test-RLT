<script setup lang="ts">
import { ref } from "vue";
import BaseModal from "./components/BaseModal.vue";
import IconClose from "./components/IconClose.vue";
import InventoryCell from "./components/InventoryCell.vue";
import ModalCell from "./components/ModalCell.vue";
import TextSkeleton from "./components/TextSkeleton.vue";

const modal = ref<InstanceType<typeof BaseModal> | null>(null);

function openModal() {
  modal.value.open();
}
</script>

<template>
  <div class="container">
    <sidebar>
      <div class="image">
        <img src="@/assets/nicebg 1.png" />
      </div>
      <TextSkeleton tag="h3" />
      <TextSkeleton width="155px" />
      <TextSkeleton width="190px" />
      <TextSkeleton width="170px" />
      <TextSkeleton width="160px" />
      <TextSkeleton width="140px" />
      <TextSkeleton width="80px" />
    </sidebar>
    <main>
      <InventoryCell
        @click="openModal"
        v-for="index in 25"
        class="cell"
        data-item-counter="3"
      />
      <BaseModal ref="modal">
        <ModalCell />
      </BaseModal>
    </main>
    <footer>
      <TextSkeleton width="699px" />
      <button class="icon-close">
        <IconClose />
      </button>
    </footer>
  </div>
</template>

<style scoped lang="scss">
.container {
  display: grid;
  gap: 24px;
  width: 785px;
  margin: auto;
  margin-top: 32px;

  grid-template-areas:
    "sidebar main"
    "footer footer";
}

sidebar {
  grid-area: sidebar;
  width: 236px;
  border: 1px solid #4d4d4d;
  background: rgb(var(--color-background-soft));
  border-radius: 12px;

  .image {
    position: relative;
    overflow: hidden;
    height: 240px;
    width: max-content;
    margin: auto;
    margin-top: 18px;
    border-radius: 8px;
    backdrop-filter: blur(6px);

    &::after {
      content: "";
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      backdrop-filter: blur(6px);
    }
  }
  h3 {
    margin: 20px auto 24px auto;
    margin-top: 20px;
    margin-bottom: 24px;
    border-radius: 8px;
    width: 190px;
    height: 26px;
  }
  p {
    margin: 16px auto;
  }
  p:last-child {
    margin: 24px auto;
  }
}

main {
  grid-area: main;
  position: relative;
  display: grid;
  gap: 1px;
  grid-template-columns: repeat(5, 1fr);
  grid-template-rows: repeat(5, 1fr);
  width: 525px;
  height: 500px;
  border: 1px solid #4d4d4d;
  background: #4d4d4d;
  border-radius: 12px;
  overflow: hidden;
}

footer {
  grid-area: footer;
  position: relative;
  border: 1px solid #4d4d4d;
  background: rgb(var(--color-background-soft));
  border-radius: 12px;

  p {
    height: 36px;
    margin: 18px;
    margin-right: auto;
  }
  .icon-close {
    position: absolute;
    top: 8px;
    right: 8px;
    border: none;
    background-color: transparent;
    display: flex;
    justify-content: center;
    align-items: center;
    width: 24px;
    height: 24px;
    cursor: pointer;
  }
}

header {
  line-height: 1.5;
  .logo {
    width: 300px;
  }
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
