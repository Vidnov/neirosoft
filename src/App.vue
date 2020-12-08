<template>
  <div id="app">
    <section class="header">
      <Header />
    </section>
    <section class="content">
      <Main  />
    </section>
    <section class="footer">
      <Footer />
    </section>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Main from "./components/Main.vue";
import Footer from "./components/Footer.vue";

export default {
  name: "App",
  components: {
    Header,
    Main,
    Footer
  },
  data() {
    return {
    
    }
  }
};
</script>

<style lang="scss">
@font-face {
  font-family: "Roboto"; /* Имя шрифта */
  src: url("./../public/fonts/Roboto/Roboto-Medium.ttf"); /* Путь к файлу со шрифтом */
}

body,
html,
div,
p {
  margin: 0;
  padding: 0;
}
h2 {
  font-family: "Roboto";
}
span {
  font-style: normal;
  font-weight: normal;
  font-size: 24px;
  line-height: 30px;
}
body {
  font-weight: 500;
  color: #353d54;
  font-size: 30px;
  line-height: 36px;
  font-family: Roboto;

  .header {
    background-color: #f0f1f4;
  }
}

.container {
       width: 80%;
    margin: 0 312px
}
</style>
