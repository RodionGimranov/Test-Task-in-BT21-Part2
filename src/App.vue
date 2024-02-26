<template>
  <nav>
    <router-link to="/" class="home-page-btn">Главная</router-link>
    <router-link to="/second-page" class="second-page-btn">О нас</router-link>
  </nav>
  <router-view/>
</template>

<script>
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;500;700&display=swap');
* {
    margin: 0;
    padding: 0;
    border: 0;
}

a {
    color: #000;
    text-decoration: none;
}

input {
    border: none;
    background: none;
    outline: none;
}

body {
    min-width: 320px;
    height: 100%;

    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: center;

    background: linear-gradient(90deg, #F5F7FA 0%, #C3CFE2 100%);
    font-family: 'Roboto', sans-serif;
    color: #000;
}

nav {
  width: 100%;

  box-sizing: border-box;
  padding-top: 20px;

  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  gap: 20px;

  font-size: 20px;
  font-weight: 500;
}

.home-page-btn,
.second-page-btn {
  color: #000;
  transition: 0.2s;
}

.home-page-btn:hover,
.second-page-btn:hover {
  color: #999;
}
</style>