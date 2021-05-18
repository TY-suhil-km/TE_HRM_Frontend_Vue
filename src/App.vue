<template>
  <div id="app">
    <!-- <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    <router-view/> -->
    <NavigationMenu/>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import NavigationMenu from "@/components/NavigationMenu.vue"
export default Vue.extend({
  name: "App",
  components: {
    NavigationMenu,
  },
})
</script>