<template>
  <div class="box"></div>
</template>

<style lang="scss">
.box {
  position: relative;
  width: 54px;
  height: 54px;

  &::before {
    content: "";
    position: absolute;
    bottom: 0;
    left: 0;
    background: hsl(random(259), random(100) * 1%, random(100) * 1%);
    width: 88.888888%;
    height: 88.888888%;
  }
  &::after {
    content: "";
    position: absolute;
    top: 0;
    right: 0;
    background: hsla(random(259), random(100) * 1%, random(100) * 1%, 0.35);
    width: 88.888888%;
    height: 88.888888%;
    backdrop-filter: blur(6px);
  }
}
</style>
