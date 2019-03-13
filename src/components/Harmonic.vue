<template>
    <div class="container__crop">
              <div v-on:click="crop" class="container__crop-title">{{title}}</div>
                    <slot></slot>
            </div>
</template>

<script>
export default {
  props: ['title'],
  methods: {
   crop: function(event) {
        event.target.parentNode.classList.toggle('open_crop');
      }
  }
}
</script>

<style lang="scss">
.container {
  &__crop {
    width: 110%;
    margin-left: -34px;
    padding: 10px 0;

    &-title {
      position: relative;
      background: #00bbd2;
      color: #fff;
      font-size: 18px;
      line-height: 1.67;
      letter-spacing: -.3px;
      font-weight: 700;
      padding: 16px 72px 16px 29px;
      cursor: pointer;
      text-align: left;
      font-family: "Montserrat";

      &:before,
      &:after {
        content: "";
        display: block;
        width: 30px;
        height: 2px;
        background: #fff;
        position: absolute;
        top: 50%;
        opacity: 0.8;
        right: 20px;
        transition: .7s;
      }

      &:after {
        transform: rotate(90deg);
      }
    }

    &.open_crop {
      .container__crop-content {
        height: auto !important;
        padding: 30px 0px;
        transition: .3s;
      }

      .container__crop-title {
        &:before {
          content: "";
          transform: rotate(360deg);
          transition: .7s;
        }

        &:after {
          content: "";
          height: 0px;
          transition: .7s;
        }
      }
    }
  }

  &__crop-content {
    height: 0;
    overflow: hidden;
    box-shadow: 0 2px 37px 0 rgba(0, 187, 210, .27);
    transition: .3s;
    padding-left: 30px !important;
    padding-right: 30px !important;
  }
}

 @media (max-width: 480px) {
   .slick-list.draggable {
     height: 726px !important;
   }

   .container__crop {
     width: 100%;
     margin: 0;
   }

   .container__crop-title {
     font-size: 15px;
     padding: 10px;
     margin-top: 34px;
   }
 }
</style>

