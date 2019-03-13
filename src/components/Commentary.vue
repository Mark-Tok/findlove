<template>
    <div class="comment-psy">
        <div class="comment-psy__header">
            <div class="comment-psy__img">
                <img src="../assets/psy.png" alt="">
            </div>
            <div class="comment-psy__content-header">
                Комментарий психолога
                <div class="comment-psy__name">
                    Вадим Захаров,
                    психолог-консультант
                </div>
            </div>
        </div>
        <div class="comment-psy__content">          
            <slot></slot>       
        </div>
    </div>
</template>

<style lang="scss">
.comment-psy {
  width: 40%;
  margin: 0 auto;
  padding: 50px 0;

  &__header {
    display: flex;
    align-items: center;
  }

  &__img {
    width: 220px;

    img {

      width: 105%;
      max-width: 100%;

    }
  }

  &__content-header {
    text-transform: uppercase;
    color: #00bbd2;
    font-size: 25px;
    line-height: 1.4;
    letter-spacing: -.4px;
    margin-bottom: 16px;
    font-weight: 700;
    font-family: Montserrat;
    margin-left: 30px;
  }

  &__name {
    font-size: 18px;
    line-height: 1.67;
    letter-spacing: -.3px;
    color: black;
    text-transform: initial;
    width: 223px;
    margin-top: 17px;
  }

  &__content {
    border-left: 8px solid #00bbd2;
    padding-left: 44px;
    margin-top: -18px;

    p {
      font-family: "Montserrat-Regular";
      font-style: normal;
      font-size: 14px;
      text-align: left;
      line-height: 1.88;
      letter-spacing: -.3px;
    }
  }
}
 @media (max-width: 1500px) {
   .comment-psy {
  width: 60%;
 }
 }
 @media (max-width: 768px) {
   .comment-psy {
  width: 91%;
 }
 }

  @media (max-width: 480px) {
 .comment-psy__header {
    flex-direction: column;
}
 }
</style>

