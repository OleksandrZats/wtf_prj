<template>
  <Header />
</template>

<script>
import Header from "./components/Header.vue";

export default {
  name: "App",
  components: {
    Header,
  },
};
</script>

<style>
@font-face {
  font-family: "GTCinetype";
  src: url("./fonts/Cinetype/GT-Cinetype-Mono.ttf") format("truetype");
  font-style: normal;
  font-weight: normal;
}
@font-face {
  font-family: "GTAlpina";
  src: url("./fonts/Alpina/GT-Alpina-Standard-Thin.ttf") format("truetype");
  font-style: normal;
  font-weight: normal;
}
* {
  box-sizing: border-box;
  padding: 0;
  margin: 0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  background-color: transparent;

  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
html {
  background: url("./assets/Background.svg") left center;
  background-size: cover;
  background-color: #d9dbda;
}
</style>
