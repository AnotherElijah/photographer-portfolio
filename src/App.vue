<template>
    <div>
    <Header></Header>
    <Router></Router>
    </div>
</template>

<script>
import Router from './components/Router.vue'
import "./css/turin-basic.css";
import "./css/turin-color.css";
import "./css/turin-fonts.css";
import "./css/turin-layout.css";
import "./css/animations.css";
import Header from "@/components/Header";



export default {
  name: 'app',
  components: {
      Header,
    Router
  }
}
</script>

<style>

</style>
