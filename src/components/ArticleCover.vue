<template>
  <div class="container__cover-article article-cover">
    <div :style="img" class="article-cover__backgound">
      <div class="article-cover__number">
        {{number}}
      </div>
    </div>
    <div class="article-cover__title">
      <slot></slot>
    </div>
  </div>
</template>

<script>
export default {
  props: ['img', 'number']
}
</script>

<style lang="scss">
@font-face {
  font-family: "Copyrighthouse";
  font-style: normal;
  font-weight: 300;
  src: url("../fonts/Copyrighthouse.ttf") format("woff2");
}

.article-cover {
  position: relative;
  border-bottom: 7px solid #00bbd2;
  margin-bottom: 60px;

  &__backgound {
    height: auto;
    width: 100%;
    background-size: contain !important;
    background-repeat: no-repeat !important;
    padding: 26% 0;
    position: relative;
    margin-top: 100px;

  }

  &__number {
    font-family: "Copyrighthouse";
    font-style: normal;
    font-weight: 300;
    color: #4dd0df;
    font-size: 160px;
    position: absolute;
    left: -61px;
    top: -67px;
  }
}
  @media (max-width: 768px) {
    .article-cover__number {
      right: auto;
      left: 0;
      top: 0;
    }

    .article-cover__title {
      left: 0;
    }

    .article-cover__title span {
      font-size: 17px;
    }
    .article-cover__backgound {
      margin-top: 50px;
    }
  }

  @media (max-width: 480px) {

    .article-cover {
      margin-bottom: 114px;
      margin-top: 50px;
    }

    .article-cover__number {
      font-size: 65px;
    }

    .article-cover__title {
      position: relative !important;
      margin-top: 51px;
      width: 100% !important;
    }
    .article-cover__backgound {
      margin-top: 0px;
    }
  }
</style>
