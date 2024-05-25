<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <div class="main">
    <div class="left-bar" v-if="!isMobileScreen">
      <NavigationBar></NavigationBar>
    </div>

    <div class="body-page">
      <div class="container">
        <div style="display: flex; gap: 5px">
          <span style="margin: auto 0px" v-if="isMobileScreen">
            <i class="mdi mdi-menu" @click="toggleMenu"></i>
            <NavigationBar
              v-if="isMenuOpen"
              @click="toggleMenu"
              class="navBar"
            ></NavigationBar>
          </span>
          <h2>Overview</h2>
        </div>
        <div class="container layout">
          <i class="mdi mdi-bell-outline icon"></i>
          <i class="mdi mdi-account-circle icon"></i>
          <div class="btn">
            Administrator<i class="mdi mdi-chevron-down"></i>
          </div>
        </div>
      </div>
      <div class="container">
        <div>
          <div>
            <Card></Card>
          </div>
          <div>
            <Table></Table>
          </div>
        </div>
        <div>
          <Products></Products>
        </div>
      </div>
    </div>
    <!-- 
    <div style="width: 18%">
      <Products></Products>
    </div> -->
  </div>
</template>
<script setup>
import NavigationBar from "./NavigationBar.vue";
import Card from "./Card.vue";
import Table from "./Table.vue";
import Products from "./Products.vue";
import { computed, ref } from "vue";

const isMenuOpen = ref(false);

const isMobileScreen = computed(() => {
  if (window.screen.width < 578) {
    return true;
  } else {
    return false;
  }
});

function toggleMenu() {
  isMenuOpen.value = !isMenuOpen.value;
}
</script>
<style scoped>
.container {
  display: flex;
  justify-content: space-between;
}
.main {
  display: flex;
  gap: 20px;
}
.icon {
  height: 32px;
  width: 32px;
  padding-right: 15px;
}
.layout {
  margin: auto 0px;
  padding-right: 40px;
}
.btn {
  border: none;
  outline: none;
  /* text-decoration: none; */
  background-color: inherit;
  cursor: pointer;
}
.left-bar {
  width: 18%;
  @media screen and (max-width: 1025px) {
    width: 18%;
  }
}
.body-page {
  width: 82%;
  @media screen and (max-width: 1025px) {
    width: 82%;
  }
  @media screen and (max-width: 578px) {
    width: 100% !important;
    padding: 0px 20px;
  }
}
.navBar {
  position: fixed;
  background-color: rgb(3, 3, 59);
}
</style>
