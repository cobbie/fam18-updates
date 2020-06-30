<template>
  <div id="app">

    <div>Progress: 
      <b-progress :value="value" variant="success" animated show-progress></b-progress> </div>
      <div>Update # :</div>
    <div>Priority level:
    <b-icon icon="star-fill" variant="warning"></b-icon>
    <b-icon icon="star-fill" variant="warning"></b-icon>
    <b-icon icon="star-fill" variant="warning"></b-icon>
    <b-icon icon="star-fill" variant="warning"></b-icon>
    <b-icon icon="star-fill" variant="warning"></b-icon></div>

  
  <div>Press any key to continue.</div>

  </div>

</template>

<script>
import Vue from 'vue'
import { BootstrapVue, IconsPlugin, BootstrapVueIcons, Star } from 'bootstrap-vue'

import 'bootstrap/dist/css/bootstrap.css'
import 'bootstrap-vue/dist/bootstrap-vue.css'

Vue.use(BootstrapVue)
// Optionally install the BootstrapVue icon components plugin
Vue.use(IconsPlugin)
Vue.use(BootstrapVueIcons)
Vue.component('Star', Star)


export default {
  name: 'App',
  components: {

  },
  data(){
    return {
      value: 25
    }
  }
}
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
