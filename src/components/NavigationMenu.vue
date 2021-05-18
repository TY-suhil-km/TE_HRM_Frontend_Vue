<template>
  <div>
    <div class="topSide"></div>
    <div class="leftSide">
      <span class="menu-icon mb-2 btn">
        <i class="fas fa-bars"></i>
      </span>
      <div class="iconContainer mx-auto">
        <span class="btn"><i class="fas fa-home"></i></span>
        <span class="btn"><i class="fas fa-crown"></i></span>
        <span class="btn"><i class="fas fa-user"></i></span>
      </div>
    </div>
  </div>
</template>
<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
@Component
export default class NavigationMenu extends Vue {
  drawer = true;
  items = [
    { title: "Home", icon: "mdi-home-city" },
    { title: "My Account", icon: "mdi-account" },
    { title: "Users", icon: "mdi-account-group-outline" },
  ];
  mini = true;
}
</script>
<style scoped>
.leftSide {
  height: 100vh;
  width: 5%;
  background-color: #2d2d72;
  /* padding: 15px ; */
  position: relative;
  top: -10px;
}
.fas {
  font-size: 20px;
  color: white;
}
.iconContainer {
  margin-top: 10px;
}
.iconContainer > .fas {
  margin-bottom: 10px;
  margin-top: 10px;
}
.fa-user {
  margin-left: 3px;
}
.topSide {
  height: 7vh;
  width: 100vw;
  position: relative;
  top: 0;
  left: 7vh;
  background-color: rgb(224, 220, 220);
}
</style>