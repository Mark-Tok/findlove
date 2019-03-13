<template>
  <div class="container__squares">
    <span></span>
    <span></span>
    <span></span>
  </div>
</template>

<style lang="scss">
.container {
  &__squares {
    position: absolute;
    width: 1200px;
    height: 500px;
    left: 0;
    right: 0;
    margin: 0 auto;
    z-index: -1;
    margin-top: -6%;
  }

  &__squares {
    span {
      width: 33%;
      height: 140px;
      background: #f3f3f4;
      display: block;
    }
  }

  &__squares {
    span {
      &:nth-child(2) {
        position: absolute;
        right: -15px;
        top: -20%;
      }

      &:nth-child(1) {
        margin-top: 0%;
      }

      &:nth-child(3) {
        position: absolute;
        margin: 0 auto;
        right: 9px;
        left: 0;
      }
    }

  }
}

@media (max-width: 1230px) {
  .container {
  &__squares {
  width: 100%;
}}}
</style>
