<template>
  <div id="app">
 <MainTabbar></MainTabbar>
    <router-view></router-view>
  </div>
</template>
<script>
import MainTabbar from './components/content/maintabbar/MainTabbar'
export default {
  name: "App",
  components:{
    MainTabbar
  }
};
</script>
<style>
@import "./assets/css/bass.css";
</style>
