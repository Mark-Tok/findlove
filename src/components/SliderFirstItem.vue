<template>
  <div class="slider__item">
    <div class="slider__title"> {{title}}</div>
    <div class="slider__content">
     <slot></slot>
    </div>
  </div>
</template>

<script>
export default {
  props: ['title']
}

$(document).ready(function () {
  $('.slider__container').slick({
    slide: '.slider__item',
    dots: true,
    infinite: true,
    speed: 200,
    slidesToShow: 1,
    adaptiveHeight: true,
    arrows: false,
  })
})
</script>

<style lang="scss">
.slider-circle {
  height: auto;
  width: 100%;
  position: relative;
  margin-top: 10px;
  z-index: 0;
  padding: 50px 0;

  &__image {
    background-image: url('../assets/back_slider_item1.png');
    height: 360px;
    background-repeat: no-repeat;
    width: 442px;
    background-size: contain;
    position: absolute;
    left: -19%;
    right: 0;
    margin: 0 auto;
    z-index: 1;
  }

  &__background {
    background: #00bbd2;
    width: 100%;
    height: 303px;
    position: absolute;
  }

  &__container {
    padding: 90px;
  }

  .slider {
    width: 620px;
    height: 487px;
    position: relative;
    background: white;
    left: 16%;
    right: 0;
    margin: 0 auto;
    z-index: 1;
    box-shadow: 0 2px 37px 0 rgba(0, 187, 210, .27);

    &__content {
      font-size: 16px;
      line-height: 1.88;
      letter-spacing: -.3px;
      font-family: Montserrat;
      font-weight: 300;
    }

    &__title {
      font-size: 18px;
      font-weight: 700;
      line-height: 1.67;
      letter-spacing: -.3px;
      font-family: Montserrat;
      margin-bottom: 18px;
    }

    &__item {
      padding: 62px;
    }
  }
}

/*style for slick*/

.slick-slider {
  height: 100%;

  ul.slick-dots {
    position: absolute;
    bottom: 0;
    display: flex !important;
    justify-content: center;
    align-items: center;
    width: 100px;
    left: 0;
    right: 0;
    margin: 0 auto;
    padding: 0;

    li {
      list-style: none;
      position: relative;
      cursor: pointer;

      button {
        font-size: 0px;
        margin: 0 20px;
        border: none;
        background: #00bbd2;
        width: 16px;
        height: 16px;
        border-radius: 100px;
        cursor: pointer;
      }

      &.slick-active {
        button {
          opacity: 0;
        }

        &:before {
          content: "";
          border: 1px solid #00bbd2;
          width: 45px;
          height: 45px;
          position: absolute;
          border-radius: 100px;
          top: -8px;
        }

        &:after {
          content: "";
          position: absolute;
          width: 5px;
          height: 5px;
          background: #00bbd2;
          left: -5px;
          right: 0;
          margin: 0 auto;
          top: 55%;
          border-radius: 100px;
        }
      }
    }
  }
}
@media (max-width: 768px) {
  .slider-circle {
    &__image {
      left: -97%;
    }

    &.slider {
      left: 4% !important;
    }
  }

}

@media (max-width: 480px) {
  .slider-circle {
    &.slider {
      width: 100% !important;
      left: 0% !important;
      height: 653px;
    }

    .slider__item {
      padding: 31px;
    }
  }

}
</style>