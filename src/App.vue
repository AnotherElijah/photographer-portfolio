<template>
    <div>
        <Header></Header>
        <router-view></router-view>
    </div>
</template>

<script>
import "./css/turin-basic.css";
import "./css/turin-color.css";
import "./css/turin-fonts.css";
import "./css/turin-layout.css";
import "./css/animations.css";
import Header from "@/components/Header";

export default {
  name: 'app',
  components: {
      Header
  }
}
</script>

<style>

</style>
