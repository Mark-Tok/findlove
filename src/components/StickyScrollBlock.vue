<template>
  <div class="container-sticky__content">
    <div class="container-sticky__columns">
      <div class="container-sticky__column">
        <div :style="background" class="container-sticky__scroll-image">
          <div class="container-sticky__scroll-title"> {{title}}
          </div>
        </div>
      </div>
      <div class="container-sticky__item2-content">
        <slot></slot>
      </div>
    </div>
  </div>
</template>
<script>
  export default {
  props: ['background', 'title']
}
</script>

<style lang="scss">.container-sticky {
  &__column {
    width: 83%;
    position: -webkit-sticky;
    position: sticky;
    top: 136px;
    height: 600px;
    margin-top: 71px;
  }

  &__columns {
    display: flex;
    width:76%;

    p {
      font-family: "Montserrat-Regular";
      font-style: normal;
      font-size: 14px;
      text-align: left;
      line-height: 1.88;
      letter-spacing: -.3px;

    }
  }

  &__item2-content {
    width: 50%;
    padding: 0 25px;
  }

  &__item2-content-title {
    font-size: 18px;
    line-height: 1.67;
    letter-spacing: -.3px;
    margin-bottom: 16px;
    font-weight: 700;
    font-family: Montserrat;
  }

  &__item2-item {
    border-bottom: 2px solid #00bbd2;
    margin-bottom: 30px;
  }

  &__scroll-image {
    position: sticky;
    top: 136px;
    height: 600px;
    background-position-x: -1300px !important;
    background-size: cover !important;
  }

  &__scroll-title {
    font-size: 25px;
    font-weight: 700;
    letter-spacing: -.4px;
    text-transform: uppercase;
    color: #00bbd2;
    line-height: normal;
    margin-bottom: 16px;
    font-family: Montserrat;
    position: absolute;
    right: 30px;
    top: -51px;
    width: 190px;
  }
}

@media (max-width: 1500px) {
  .container-sticky {
    &__columns {
      display: flex;
      width: 82%x;
    }
    &__scroll-image {
      background-position-x: -1441px !important;
    }
  }
}

@media (max-width: 1024px) {
  .container-sticky {
    &__column {
      width: 58%;
    }

    &__item2-content {
      width: 71%;
    }

    &__scroll-image {
      background-position-x: -1597px !important;
    }
  }
}
@media (max-width: 768px) {
  .container-sticky {
    &__columns {
      flex-direction: column;
      width: 100%;
    }

    &__column {
      position: relative;
      width: 100%;
      overflow: hidden;
      margin: 0;
      height: auto;
    }

    &__scroll-image {
      background-size: cover !important;
      position: relative;
      top: 0;
      padding-bottom: 51%;
      height: auto;
      background-position: center center !important;
    }

    &__content {
      margin-top: -130px;
      width: 100%;
      position: relative;
    }

    &__item2-content {
      width: 100%;
      position: relative;
      margin: 0;
      padding: 0;
      margin-top: 167px;
    }

    &__item2-item {
      width: 84%;
      margin: 0 auto;
      margin-bottom: 20px;
    }

    &__item2-content-title {
      width: 84%;
      margin: 0 auto;
    }
  }
}

</style>
