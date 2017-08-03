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
  * {
    box-sizing: border-box;
  }
  html, body {
    min-height: 100%;
    background: #f9f9f9;
    margin: 0;
    padding: 0;
    font-family: 'Montserrat', 'Avenir', Helvetica, Arial, sans-serif;
  }
  img {
    max-width: 100%;
    height: auto;
  }
  a {
    text-decoration: none;
  }
  ul {
    list-style: none;
    margin-left: 0;
    padding-left: 24px;
    margin-top: 2rem;
  }
  li {
    margin-top: 6px;
    line-height: 1.45;
  }
  .container {
    max-width: 900px;
    margin: 0 auto;
    text-align: left;
  }
  .container p {
    line-height: 1.45;
    margin-top: 2rem;
  }
  #app {
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
