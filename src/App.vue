<template>
  <MainHeader v-show="showHeader" />
  <div v-show="showName">
    <div>Nome : {{ firstName }}</div>
    <div>Sobrenome : {{ lastName }}</div>
  </div>

  <div v-show="showLevel">
      <div v-if="accessLevel === 'admin'">Nivel Admin</div>
      <div v-else-if="accessLevel === 'marketing'">Nivel Marketing</div>
      <div v-else >Usuário Comum</div>
  </div>

  <!-- <img alt="Vue logo" src="./assets/logo.png" /> -->
  <!-- <HelloWorld msg="Welcome to Your Vue.js App" /> -->
</template>

<script>
// import HelloWorld from "./components/HelloWorld.vue";
import MainHeader from "./components/MainHeader.vue";

export default {
  name: "App",
  components: {
    // HelloWorld,
    MainHeader,
  },
  data() {
    return {
      showHeader: true,
      firstName: "Jon",
      lastName: "Snow",
      showName: true,
      showLevel: true, 
      accessLevel: ''
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
