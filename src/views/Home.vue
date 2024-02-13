<template>
  <Head_er />

  <Welcome />
  <AboutMe />
</template>

<script setup>
import Head_er from "@/components/Head_er.vue";
import Welcome from "@/components/Welcome.vue";
import AboutMe from "@/components/AboutMe.vue";
</script>

<style scoped>
h1 {
  font-size: 50px;
}

li {
  list-style: none;
}

a {
  text-decoration: none;
}
</style>
