<template>
  <div id="header" class="header">
    <div v-on:click="close" class="header__close"></div>
    <div class="header__menu">  
      <div class="header__title">Как найти свою любовь</div>
      <ul class="header__navigation">
        <li>
          <a href="#item1">01</a>
          <a href="#item2">02</a>
          <a href="#item3">03</a>
          <a href="#item4">04</a>
          <a href="#item5">05</a>
        </li>

      </ul>
      <div class="header__logo">
        <a href>
          <img src="../assets/scarlet.svg" alt>
        </a>
        <a href>
          <img src="../assets/logo-red.svg" alt>
        </a>
      </div>
    </div>
    <div id="side" class="header__progress"></div>
  </div>
</template>
<script>
export default {
  methods: {
    handleScroll() {
      var side = document.getElementById('side')
      var header = document.getElementById('header')
      var body = document.querySelector('body').getBoundingClientRect()
      var val = (window.pageYOffset * 130) / body.height
      side.style.width = val + '%'
      if (window.pageYOffset == 0) {
        header.classList.remove('show')
      } else {
        header.classList.add('show')
      }
    },
    close: function (event) {
      event.target.parentNode.classList.add('close');
    }
  },
  created() {
    window.addEventListener('scroll', this.handleScroll)
  }
}
</script>
<style lang="scss">
@font-face {
  font-family: "Montserrat";
  font-style: normal;
  font-weight: 300;
  src: url("https://fonts.gstatic.com/s/montserrat/v12/JTUSjIg1_i6t8kCHKm459W1hyzbi.woff2") format("woff2");
}

@font-face {
  font-family: "Montserrat";
  font-style: normal;
  font-weight: 500;
  src: url(https://fonts.gstatic.com/s/montserrat/v12/JTURjIg1_i6t8kCHKm45_cJD3gnD_g.woff2) format("woff2");
}

.header {
  font-family: "Montserrat";
  height: 0px;
  width: 97%;
  background: #ffffff;
  position: fixed;
  top: 0;
  left: 64px;
  overflow: hidden;
  transition: 0.2s;
  z-index: 20;
  display: flex;

  &__menu {
    display: flex;
    align-items: center;
    width: 53%;
    height: 100%;
    font-family: "Montserrat";
    font-style: normal;
    font-weight: 500;
  }

  &__close {
    width: 28px;
    cursor: pointer;
    position: relative;
    margin: 0px 64px;

    &:before,
    &:after {
      content: "";
      display: block;
      width: 29px;
      height: 2px;
      position: absolute;
      top: 50%;
      background-color: black;
      transition: background-color 1s cubic-bezier(0.19, 1, 0.22, 1);
      transform: rotate(45deg);
    }

    &:after {
      transform: rotate(45deg);
    }

    &:before {
      transform: rotate(-45deg);
    }
  }

  &__title {
    text-transform: uppercase;
    font-size: 18px;
    font-weight: 500;
    line-height: normal;
    font-weight: 300;
    font-family: "Montserrat";
  }

  &__navigation {
    list-style: none;
    display: flex;
    margin-left: 22px;

    li {
      margin-right: 30px;
      font-size: 18px;

      a {
        text-decoration: none;
        border-bottom: 4px solid #ffffff;
            color: black;
            padding: 0 19px;

        &:hover {
          color: #00bbd2;
          text-decoration: none;
          border-bottom: 4px solid #00bbd2;
        }
      }
    }
  }

  &__logo {
    position: absolute;
    right: 32px;

    a {
      margin-right: 22px;
    }
  }
  &.close {
    margin-top: -79px;
 }
}

#side {
  position: absolute;
  bottom: 0;
  height: 2px;
  width: 0%;
  background: #00bbd2;
}

.show {
  height: 67px;
  transition: 0.2s;
}

 @media (max-width: 1289px) {
   .header {
     &__title {
       font-size: 10px !important;
     }
   }
   }


   @media (max-width: 1000px) {
     .header {
       display: none;
     }
   }

   @media (max-width: 1024px) {
     .header {
       &__close {
         margin: 0px 23px;
       }

       &__title {
         font-size: 13px;
       }
     }
   }

   @media (max-width: 768px) {
     .container {
       &__header {
         width: 79%;
         padding: 0 37px !important;
         margin: 0 auto;
       }
     }
   }
</style>
