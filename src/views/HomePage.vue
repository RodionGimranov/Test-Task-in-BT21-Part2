<template>
    <div class="wrapper">
      <StartButtonComponent @click="togglePopup"></StartButtonComponent>
      <PopupMenuComponent :visible="popupVisible" @close="closePopup" @submit="handleSubmit"></PopupMenuComponent>
      <div v-if="submittedData">
        <h2>Данные анкеты:</h2>
        <ul>
          <li>Имя: {{ submittedData.name }}</li>
          <li>Возраст: {{ submittedData.age }}</li>
          <li>Номер телефона: {{ submittedData.phone }}</li>
          <li>Ник в Telegram: {{ submittedData.telegram }}</li>
          <li>Адрес: {{ submittedData.address }}</li>
        </ul>
      </div>
    </div>
  </template>
  
<script>
import StartButtonComponent from '../components/StartButton.vue';
import PopupMenuComponent from '../components/PopupMenu.vue';
  
export default {
    components: {
        StartButtonComponent,
        PopupMenuComponent
        },
    data() {
      return {
        popupVisible: false,
        submittedData: null
      };
    },
    methods: {
      togglePopup() {
        this.popupVisible = !this.popupVisible;
      },
      closePopup() {
        this.popupVisible = false;
      },
      handleSubmit(formData) {
        this.submittedData = formData;
        this.popupVisible = false;
      }
    }
}
</script>
  
<style>
.wrapper {
    width: 100%;
    height: 100vh;

    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    gap: 50px;
}

h2 {
    margin-bottom: 10px;
}

li {
    font-size: 18px;
    font-weight: 400;
}
</style>