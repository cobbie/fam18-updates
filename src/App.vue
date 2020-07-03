<template>
  <div id="app" @keyup.right="plus" @keyup.left="minus" tabindex="0">
    <div>
      Progress:
      <b-progress class="w-75 mb-3 progress" :value="value" variant="success"></b-progress>
      <!-- <div><img src="./assets/RAFACHUA.png" /> <img src="./assets/SASATY.png" /> <img src="./assets/JAYREBOSA.png" /> <img src="./assets/AJGARCIA.png" /> <img src="./assets/TONICORTES.png" /></div> -->
    </div>
    <h2>Update # {{ update }}:</h2>
    <h1 class="animate__animated animate__pulse animate__repeat-3">{{ updateText[update] }}</h1>
    <div class="priority">
      <h3>
        Priority level:
      
      <b-icon :icon="stars[0]" variant="warning" ></b-icon>
      <b-icon :icon="stars[1]" variant="warning"></b-icon>
      <b-icon :icon="stars[2]" variant="warning"></b-icon>
      <b-icon :icon="stars[3]" variant="warning"></b-icon>
      <b-icon :icon="stars[4]" variant="warning"></b-icon></h3>
    </div>

    <span>
      <!-- <b-icon icon="arrow-left-square-fill" @click="minus" v-on:keyup.right="plus"></b-icon>

      <b-icon icon="arrow-right-square-fill" @click="plus" v-on:keyup.left="minus"></b-icon> -->

      <!-- <span v-on:keyup.right="plus"></span>
      <span v-on:keyup.left="minus"></span>
      <a href="">Next Update</a>
      <a href="">Previous update</a> -->
    </span>
  </div>
</template>

<script>
import Vue from "vue";
import "animate.css"
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
  created: function () {
            window.addEventListener('keyup.right', this.plus)
    },
  data() {
    return {
      value: 0,
      update: 0,
      updateText: [
        "hello (general updates)",
        "thesis",
        "the past year",
        "career path",
        "internship at P&G",
        "the big news"
      ],
      start: [true, true, false, false, false],
      stars: ["star-fill", "star","star","star","star"]
    };
  },

  methods: {
    plus: function() {
      if(this.update < 5){
      this.update += 1;
      this.value += 20;
      this.stars[this.update] = "star-fill"
      }
      console.log('plus')
    },
    minus: function() {
      this.stars[this.update] = "star"
      this.update -= 1;
      this.value -= 20;
      console.log("minus")
    }
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

#app:focus {
    outline: 0px solid transparent;
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
  margin-top:50px;
}

h2 {
  margin-top: 120px;
}

.priority{
  margin-top: 150px;
}

img {
height: auto; 
    width: auto; 
    max-height: 100px;
}
</style>
