<template>
  <div id="app">
    <div id="nav" class="bg-info text-white">
      <!-- <router-link to="/">Home</router-link>|
      <router-link to="/about">About</router-link>-->
      <h1>
        Moody-
        <img class="vue-v" src="./assets/logo.png" />ittens
      </h1>
    </div>
    <router-view />
  </div>
</template>

<style>
.vue-v {
  height: 1em;
  transform: rotate(90deg);
  border-bottom: 10px solid green;
  margin-right: 10px
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
