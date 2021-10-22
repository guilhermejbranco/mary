<template>
  <div id="app">
    <div class="bg" v-if="clicked"></div>
    <a href="ticket.pdf" download="download" v-if="!clicked">
      <button @click="start">Receber mini-prenda extra</button>
    </a>
    <h1 v-if="clicked">Parabéns Mary!</h1>
    <img src="gui.jpg" alt="" style="width:100%" v-if="clicked" />
  </div>
</template>

<script>
import Vue from "vue";
import VueConfetti from "vue-confetti";

Vue.use(VueConfetti);
export default {
  name: "App",
  data() {
    return {
      clicked: false,
    };
  },
  components: {},
  methods: {
    start() {
      this.$confetti.start({ defaultSize: 4 });
      this.clicked = true;
    },
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
button {
  background-color: #28a745;
  color: white;
  padding: 1rem;
  border: none;
  border-radius: 5px;
  font-size: 1.4rem;
}

.bg {
  height: 100vh;
  width: 100vw;
  position: absolute;
  top: 0;
  left: 0;
  background-image: url("./assets/mary.jpg");
  background-size: cover;
  background-position: center center;
  z-index: -1;
  opacity: 0.2;
}
</style>
