<template>
  <div id="app">
    <div>
      <img class="whcus" src="@/assets/like.jpg" alt="" />
    </div>
    <HelloWorld />
    <div>
      Copyright (c) {{ date }}
      <b-link href="https://www.facebook.com/thainguyen.mta/" target="blank"
        >ThaiND</b-link
      >
    </div>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
  },
  data() {
    return {
      date: 0,
    };
  },
  created() {
    let n = new Date();
    let y = n.getFullYear();
    let m = n.getMonth() + 1;
    let d = n.getDate();
    this.date = d + "/" + m + "/" + y;
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
.copyright {
  position: relative;
}

.whcus {
  width: 500px;
  height: 400px;
}
</style>
