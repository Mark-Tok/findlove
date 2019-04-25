<template>
  <div class="side-bar">
    <div class="side-bar__full">
      <div class="side-bar__nav-container">
        <ul class="side-bar__nav">
          <li><a href='/'>Главная</a></li>
          <li><a href='/'>
              КАК НАЙТИ СВОЮ ЛЮБОВЬ
            </a>
            <a href="">Гид для тех, кто хочет влюбиться</a>
          </li>
        </ul>
      </div>
    </div>
    <div v-on:click="full" class="side-bar__toggle">
    </div>
     <div class="side-bar__logo">
           <img src="../assets/scarlet_white.svg" alt>
          <img src="../assets/logo_white.svg" alt="">
        </div>
    <div class="side-bar__share">
      <div class="side-bar__share__link"><a href=""><img src="../assets/facebook.svg" alt=""></a></div>
      <div class="side-bar__share__link"><a href=""><img src="../assets/vk.svg" alt=""></a></div>
      <div class="side-bar__share__link"><a href=""><img src="../assets/twitter.svg" alt=""></a></div>
      <div class="side-bar__share__back">
        <img src="../assets/arrow.svg" alt="">
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'SideBar',
      methods: {
      full: function (event) {
        event.target.parentNode.childNodes[0].classList.toggle('open_full');
        event.target.classList.toggle('close');

      }
    }
}
</script>

<style lang="scss">
  .side-bar {
    background: #00bbd2;
    height: 100vh;
    width: 64px;
    position: fixed;
    left: 0;
    z-index: 30;

    &__full {
      position: fixed;
      width: 100vw;
      height: 100vh;
      background: #00bbd2;
      left: -100%;
      transition: .3s;
      display: flex;
      justify-content: center;
      align-items: center;
    }

    
    &__logo{
      display: none;
    }

    &__toggle {
      width: 63px;
      height: 55px;
      position: absolute;
      top: 46px;
      cursor: pointer;

      &:after,
      &:before {
        content: "";
        display: block;
        width: 30px;
        height: 2px;
        position: absolute;
        transition: .3s;
        background-color: white;
        transform: rotate(0deg);
        left: 0;
        right: 0;
        margin: 0 auto;
      }

      &:before {
        top: 60%;
      }

      &:after {
        top: 35%;
      }

      span {
        display: flex;
        width: 55%;
        background: white;
        height: 2px;
        padding: 0px;
        flex-direction: column;
        margin: 0 auto;

        &:nth-child(1) {
          margin-bottom: 13px;
        }
      }
    }

    &__share {
      position: absolute;
      bottom: 0;

      &__link {
        height: 64px;
        width: 64px;

        a {
          width: 100%;
          display: block;
          background: #4dd0df;
          height: 100%;
          transition: .2s;
          align-items: center;
          justify-content: center;
          display: flex;

          &:hover {
            background: #00bbd2;
            transition: .2s;
          }
        }
      }

      &__back {
        height: 124px;
        display: -ms-flexbox;
        display: flex;
        -ms-flex-align: center;
        align-items: center;
        -ms-flex-pack: center;
        justify-content: center;
        background: #f1f1f2;
      }
    }

    .open_full {
      left: 62px;
    }
  }

  .close {
    &:before {
      transform: rotate(225deg);
      transition: .5s;
      top: 19px;
    }

    &:after {
      transform: rotate(-45deg);
      transition: .5s;
    }
  }

  .side-bar {
    &__nav-container {
      display: flex;
      justify-content: center;
      align-items: center;
      margin-left: -21%;
      width: 61%;
    }

    &__nav {
      color: white;
      padding: 0px 54px;
      width: 20%;
      border-right: 1px solid;

      li {
        cursor: pointer;
        list-style: none;
        margin: 33px 0;
        text-transform: uppercase;
        font-size: 25px;
        line-height: 1.4;
        letter-spacing: -.4px;
        font-weight: 700;
        font-family: Montserrat;

        a {
          text-decoration: none;
          color: white;
        }

        &:nth-child(2) {
          display: flex;
          flex-direction: column;

          a {
            margin: 14px 0;

            &:nth-child(2) {
              text-transform: initial;
              font-size: 17px;
              font-weight: 300;
              font-family: Montserrat;
            }
          }
        }
      }
    }
  }
  .side-bar__authors {
    li {
      color: white;
      list-style: none;
      font-family: Montserrat;
      font-weight: 300;
      margin: 11px 0;
    }
  }
    @media (max-width: 1280px) {
      .side-bar {
        &__nav {
          width: 30%;
        }
      }
    }

    @media (max-width: 1280px) {
      .side-bar {
        &__nav {
          width: 58%;

        }
      }
    }

    @media (max-width: 768px) {
      .side-bar {
        height: 62px;
        width: 100vw;
        position: fixed;
        left: 0;
        z-index: 30;

        &__share {
          display: none;
        }

        &__toggle {
          top: 4px;
        }

        &__full {
          left: 0;
          top: -100%;

        }

        &__logo {
          display: block;
          position: absolute;
          right: 24px;
          top: 23px;

          img {
            margin: 0 14px;
          }
        }

        .open_full {
          top: 0;
          left: 0;
        }

        &__nav-container {
          flex-direction: column;
          width: 105%;
          margin: 0;
          justify-content: left;
          align-items: start;
          height: calc(100% - 64px);
          position: fixed;
          overflow-y: scroll;
          margin-top: 33px;
        }

        ul.side-bar__nav {
          border-right: none;
          width: 85%;
          padding: 0 42px;

          li {
            margin: 0px -6px;
          }
        }
      }
    }
</style>
