<template>
  <div class="slider__item4">
    <div class="slider__title">{{title}}</div>
    <p>
      <slot></slot>
    </p>
  </div>
</template>

<script>
export default {
  props: ['title']
}
$(document).ready(function () {
  var $status = $('.pagingInfo');
  var $slickElement = $('.slider');
  var item = document.querySelectorAll('.slider__item4');

  $slickElement.on('init reInit afterChange', function (event, slick, currentSlide, nextSlide) {
    var i = (currentSlide ? currentSlide : 0) + 1;
    $status.html('<span class="current_slide">' + i + '</span>' + '<span class="all_slide">' + item.length + '</span>');
  });
  $slickElement.slick({
    slide: '.slider__item4',
    autoplay: false,
    dots: false,
    infinite: true,
    speed: 200,
    slidesToShow: 1,
    adaptiveHeight: true,
    arrows: true,
  });
})
</script>

<style lang="scss">
.content__item4 {
  &.slider {
    box-shadow: 0 2px 37px 0 rgba(0, 187, 210, .27);
    padding: 56px;
    width: 120%;
    margin-left: -10%;
    margin-bottom: 67px;
    background: white;

    &__title {
      font-size: 18px;
      font-weight: 700;
      line-height: 1.67;
    }
  }

}

.slider {
  &:before {
    content: "";
    background: #4dd0df;
    opacity: .32;
    height: 21px;
    position: absolute;
    bottom: -20px;
    width: 100%;
    left: 0;
    z-index: 0;
  }

  &:after {
    content: "";
    background: #4dd0df;
    opacity: .32;
    height: 33px;
    position: absolute;
    bottom: -34px;
    width: 92%;
    left: 0;
    z-index: 0;
    right: 0;
    left: 0;
    margin: 0 auto;
  }

  &__title {
    font-size: 18px;
    line-height: 1.67;
    letter-spacing: -.3px;
    margin-bottom: 16px;
    font-weight: 700;
    font-family: Montserrat;
    text-align: left;
  }

  &__item4 {
    height: 300px;
    max-height: 800px;
  }

  button.slick-prev.slick-arrow {
    font-size: 21px;
    background: #535353;
    border: none;
    width: 100px;
    cursor: pointer;
    height: 1px;
    margin: 10px 0;
    color: rgba(255, 255, 255, 0.03);
    line-height: 0;
    right: 166px;

    &:after,
    &:before {
      content: "";
      width: 12px;
      height: 2px;
      background: #535353;
      position: absolute;
      left: 0px;
    }

    &:after {
      transform: rotate(-52deg);
      top: -5px;
      left: -2px;
    }

    &:before {
      transform: rotate(52deg);
      top: 5px;
      left: -1px;
    }
  }

  button.slick-next.slick-arrow {
    font-size: 21px;
    background: #535353;
    border: none;
    width: 100px;
    cursor: pointer;
    height: 1px;
    margin: 10px 0;
    color: rgba(255, 255, 255, 0.03);
    line-height: 0;

    &:after,
    &:before {
      content: "";
      width: 12px;
      height: 2px;
      background: #535353;
      position: absolute;
      right: 0px;
    }

    &:after {
      transform: rotate(52deg);
      top: -5px;
      right: -2px;
    }

    &:before {
      transform: rotate(-52deg);
      top: 5px;
      right: -1px;
    }
  }

  .slick-arrow {
    position: absolute;
    bottom: 12px;
    right: -27px;
  }

  span.pagingInfo {
    position: absolute;
    bottom: 0;
    right: 105px;
    font-family: "Montserrat";
    display: flex;
  }

  span.current_slide {
    font-weight: 600;
    color: #00bbd2;
    margin-right: 8px;
    font-size: 40px;
  }

  span.all_slide {
    padding-top: 18px;
    margin-right: -19px;
    padding-left: 12px;
  }
}

@media (max-width: 768px) {
  .content__item4.slider {
    width: 99%;
    margin: 0 auto;
  }
}

@media (max-width: 480px) {
  .slick-list.draggable {
    height: 726px !important;
  }

  .content__item4.slider {
    height: 691px !important;
    padding: 20px;
  }
}
</style>
