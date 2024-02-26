<template>
    <section class="pop-up__menu__container" v-show="visible" @click.self="closePopup">
      <div class="pop-up__menu__content">
        <h1 class="pop-up__title">Анкета участника</h1>
        <div class="input__list__container">
          <input class="user__name" type="text" placeholder="Ваше имя" required v-model="name">
          <input class="user__age" type="text" placeholder="Ваш возраст" required v-model="age">
          <input class="user__mobile-phone" type="number" placeholder="Номер телефона"
            minlength="8" maxlength="12" autocomplete="tel" required v-model="phone">
          <input class="user__telegram" type="text" placeholder="Ник в Telegram" required v-model="telegram">
          <input class="user__adress" type="text" placeholder="Ваш адрес" required v-model="address">
        </div>
        <button class="send__data__btn" @click="submitForm">Отправить</button>
      </div>
    </section>
  </template>
  
<script>
  export default {
    props: {
      visible: Boolean
    },
    data() {
      return {
        name: '',
        age: '',
        phone: '',
        telegram: '',
        address: ''
      };
    },
    methods: {
      closePopup() {
        this.$emit('close');
      },
      submitForm() {
        const formData = {
          name: this.name,
          age: this.age,
          phone: this.phone,
          telegram: this.telegram,
          address: this.address
        };
        this.$emit('submit', formData);
      }
    }
  }
</script>

<style>
.pop-up__menu__container {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    min-height: 100vh;
    z-index: 9999;

    box-sizing: border-box;
    padding: 10px;

    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;

    background: rgba(0, 0, 0, 0.5);
    backdrop-filter: blur(5px);
}

.pop-up__menu__content {
    max-width: 400px;

    background-color: #fff;
    border-radius: 10px;
    box-sizing: border-box;
    padding: 15px;

    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    gap: 20px;
}

.pop-up__title {
    font-size: 36px;
    font-weight: 500;
    color: #000;
    text-align: center;
}

.input__list__container {
    width: 100%;

    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: flex-start;
    flex-wrap: wrap;
    gap: 15px;
}

.user__name,
.user__age,
.user__mobile-phone,
.user__telegram,
.user__adress {
    width: 47%;
    height: 46px;

    background: #fff;
    box-shadow: 0px 0px 40px 5px rgba(0, 0, 0, 0.25); border-radius: 10px;
    box-sizing: border-box;
    padding: 0px 10px;

    font-size: 16px;
    font-weight: 500;
    color: #000;
    font-family: 'Roboto', sans-serif;
}

.user__adress {
    width: 100%;
}

input[type="number"]::-webkit-inner-spin-button,
input[type="number"]::-webkit-outer-spin-button {
  -webkit-appearance: none;
  margin: 0;
}

input[type="number"] {
    appearance: textfield;
    -moz-appearance: textfield;
}

::placeholder {
    font-size: 16px;
    font-weight: 400;
    color: #999;
    font-family: 'Roboto', sans-serif;
}

.send__data__btn {
    box-sizing: border-box;
    padding: 8px 14px;

    border-radius: 6px;
    background-color: #4F82E5;
    transition: 0.2s;

    font-size: 24px;
    font-weight: 500;
    color: #fff;
    user-select: none;
    -webkit-user-select: none;
}

.send__data__btn:active {
    transform: scale(0.97);
}

@media (max-width: 768px) {
    .user__name,
    .user__age,
    .user__mobile-phone,
    .user__telegram,
    .user__adress {
        width: 100%;
    }
}
</style>