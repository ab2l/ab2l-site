<template>
  <div id="app">
    <header class="Header">
      <img class="Header__logo" src="./assets/logo.png">
    </header>
    <router-view></router-view>
  </div>
</template>

<script>
export default {
  name: 'app',
};
</script>

<style>
  html, body {
    min-height: 100%;
    background: #f9f9f9;
    margin: 0;
    padding: 0;
  }
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    padding-bottom: 48px;
  }
  .Header {
    background: #fff;
    display: flex;
    align-items: center;
    justify-content: center;
    min-height: 200px;
    user-select: none;
  }
  .Header__logo {
    max-width: 236px;
    width: 100%;
  }
</style>
