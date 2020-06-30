<template>
  <div id="app">
    <div  @keydown.right="plus">
      Progress:
      <b-progress class="w-75 mb-3 progress" :value="value" variant="success"></b-progress>
    </div>
    <h2>Update # {{ update }}:</h2>
    <h1>{{ updateText[update] }}</h1>
    <div>
      Priority level:
      <b-icon icon="star-fill" variant="warning"></b-icon>
      <b-icon icon="star-fill" variant="warning"></b-icon>
      <b-icon icon="star-fill" variant="warning"></b-icon>
      <b-icon icon="star-fill" variant="warning"></b-icon>
      <b-icon icon="star-fill" variant="warning"></b-icon>
    </div>

    <span>
      <b-icon icon="arrow-left-square-fill" @click="minus" v-on:keyup.right="plus"></b-icon>

      <b-icon icon="arrow-right-square-fill" @click="plus" v-on:keyup.left="minus"></b-icon>

      <span v-on:keyup.right="plus"></span>
      <span v-on:keyup.left="minus"></span>
    </span>
  </div>
</template>

<script>
import Vue from "vue";
import {
  BootstrapVue,
  IconsPlugin,
  BootstrapVueIcons,
  Star
} from "bootstrap-vue";
import "bootstrap/dist/css/bootstrap.css";
import "bootstrap-vue/dist/bootstrap-vue.css";

Vue.use(BootstrapVue);
Vue.use(IconsPlugin);
Vue.use(BootstrapVueIcons);
Vue.component("Star", Star);

export default {
  name: "App",
  components: {},
  created: function () {
            window.addEventListener('keyup.right', this.plus)
    },
  data() {
    return {
      value: 20,
      update: 1,
      updateText: [
        "Hello",
        "Thesis",
        "The past year",
        "Career Path",
        "Internship at P&G",
        "No title. Just words."
      ],
      start: [true, true, false, false, false]
    };
  },

  methods: {
    plus: function() {
      this.update += 1;
      this.value += 20;
      console.log('plus')
    },
    minus: function() {
      this.update -= 1;
      this.value -= 20;
      console.log("minus")
    }
  }
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
  width: 20px;
  height: 20px;
}
.progress {
  margin: 0 auto;
  margin-top: 10px;
}

h1 {
  font-size: 100px;
}

h2 {
  margin-top: 50px;
}
</style>
