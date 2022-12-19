<script lang="ts">
import IconClose from "./IconClose.vue";

export default {
  data() {
    return {
      isOpen: false,
    };
  },
  methods: {
    open() {
      this.isOpen = true;
    },
    close() {
      this.isOpen = false;
    },
  },
  components: { IconClose },
};
</script>

<template>
  <Transition name="modal">
    <div v-if="isOpen" class="modal">
      <button @click="close" class="icon-close">
        <IconClose />
      </button>
      <slot></slot>
    </div>
  </Transition>
</template>

<style scoped lang="scss">
.modal {
  position: absolute;
  right: 0;
  min-width: 250px;
  height: 100%;
  background-color: rgba(var(--color-background-soft), 0.5);
  border-left: 1px solid #4d4d4d;
  backdrop-filter: blur(8px);
  transform: translateX(0px);

  .icon-close {
    position: absolute;
    right: 14px;
    top: 14px;
    border: none;
    background-color: transparent;
    display: flex;
    justify-content: center;
    align-items: center;
    width: 12px;
    height: 12px;
    padding: 0;
    cursor: pointer;
  }
}

.modal-enter-active,
.modal-leave-active {
  transition: all 9.5s ease;
}

.modal-enter-from,
.modal-leave-to {
  transform: translateX(250px);
}
</style>
