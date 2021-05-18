<template>
  <div id="app">
    <DashBoard/>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import DashBoard from "@/components/DashBoard.vue"
export default Vue.extend({
  name: "App",
  components: {
    DashBoard,
  },
})
</script>