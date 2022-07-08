<script setup>
import HeaderComp from "@/components/template/HeaderComp.vue";
import FooterComp from "@/components/template/FooterComp.vue";
</script>

<template>
  <HeaderComp />
  <main><RouterView /></main>
  <FooterComp />
</template>

<style>
@import url("https://fonts.googleapis.com/css2?family=Cinzel&display=swap");

#app {
  max-width: 1280px;
  margin: 0 auto;
  height: 100vh;
  font-weight: normal;
}

* {
  font-family: "Cinzel", serif;
}

main {
  height: 80%;
}

a {
  color: inherit;
  text-decoration: none;
}

/* .router-link-active {
  color: rgb(38, 83, 83);
} */
</style>
