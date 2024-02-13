<template>
  <Head_er />

  <Welcome />
  <AboutMe />
  <Skills />
  <ProjectDetail />
</template>

<script setup>
import Head_er from "@/components/Head_er.vue";
import Welcome from "@/components/Welcome.vue";
import AboutMe from "@/components/AboutMe.vue";
import Skills from "@/components/Skills.vue";
import ProjectDetail from "@/components/ProjectDetail.vue";
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
