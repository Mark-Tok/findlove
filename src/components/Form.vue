<template>
  <div class="article-form">
    <div class="article-form__auth">
      <p>Войти с помощью</p>
      <button>
        <img src="../assets/vk.svg" alt>
      </button>
    </div>
    <div class="article-form__message">
      <p>Сообщение</p>
      <textarea></textarea>
    </div>
    <div class="article-form__label">
      <div>
        <input id="check1" type="checkbox">
        <span></span>
        <label for="check1">Принимаю условия пользовательского соглашения</label>
      </div>
      <input id="check2" class="checkmark" type="checkbox">
      <span></span>
      <label for="check2">Согласен с условиями конкурса</label>
    </div>
    <button class="article-form__submit">
      <img src="../assets/submit.svg" alt>
    </button>
  </div>
</template>

<style lang="scss">
  @font-face {
    font-family: "Montserrat";
    font-style: normal;
    font-weight: 600;
    src: url("../fonts/Montserrat-Bold.ttf") format("woff2");
  }

  .article-form {
    box-shadow: 0 2px 37px 0 rgba(0, 187, 210, 0.27);
    width: 66%;
    margin: 0 auto;
    padding: 36px 106px;
    text-align: left;
    position: relative;
    font-family: "Montserrat";
    font-weight: 700;
    font-size: 18px;
    color: #9b9b9b;
    line-height: 1.67;
    font-weight: 700;

    &__auth {
      button {
        background-color: #4a76a8;
        border: none;
        width: 214px;
        height: 55px;
        transition: 0.2s;
        cursor: pointer;

        &:focus {
          outline: none;
        }

        &:hover {
          background-color: #2f4e71;
          transition: 0.2s;
        }
      }
    }

    &__message {
      padding: 50px 0;
    }

    textarea {
      width: 82%;
      border: none;
      border-bottom: 1px solid #9d9d9d;
      resize: none;
      font-size: 18px;
      margin-top: 20px;

      &:focus {
        outline: none;
      }
    }

    &__submit {
      position: absolute;
      height: auto;
      left: auto;
      top: 0;
      bottom: 0;
      right: 0;
      width: 93px;
      border: none;
      background: #4dd0df;
      cursor: pointer;
      transition: .2s;

      img {
        width: 40px;
      }

      &:hover {
        background: #00bbd2;
        transition: .2s;
      }
    }

    &__label {
      div {
        position: relative;
        margin-bottom: 20px;
      }

      input {
        position: relative;
        z-index: 1;
        opacity: 0;
        width: 24px;
        height: 21px;
        cursor: pointer;
      }

      label {
        margin-left: 10px;
      }

      span {
        width: 27px;
        height: 27px;
        border: 1px solid #6b6b6b;
        border-radius: 100px;
        display: block;
        margin-top: -29px;
        margin-left: 0px;
        position: relative;
        position: absolute;
      }
    }

    &__label input:checked~span {
      border: 1px solid #00bbd2;

      &:before {
        content: "";
        width: 7px;
        height: 7px;
        background: #00bbd2;
        position: absolute;
        border-radius: 100px;
        top: 36%;
        right: 1px;
        left: 0;
        margin: 0 auto;
      }
    }
  }
   @media (max-width: 768px) {
     .article-form {
       padding: 47px;
       width: 78%;
       padding-bottom: 108px;
     }

     button.article-form__submit {
       height: 78px;
       width: 100%;
       bottom: 0;
       top: auto;
     }

     .article-form__label label {
       font-size: 15px;
     }
   }
</style>
