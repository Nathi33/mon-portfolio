<template>
  <header class="header">
    <h2 class="logo">
      <a @click.prevent="navigateAndScroll('welcome')">Nath Drnt</a>
    </h2>

    <nav class="navBar">
      <ul class="menu_navBar">
        <li>
          <!-- Active permet de souligner lorsque l'élément du menu est  actif-->
          <!-- Prevent permet d'empêcher le comportement par défaut des liens -->
          <a
            :class="{ active: activeSection === 'welcome' }"
            @click.prevent="navigateAndScroll('welcome')"
            >Accueil</a
          >
        </li>
        <li>
          <a
            :class="{ active: activeSection === 'aboutMe' }"
            @click.prevent="navigateAndScroll('aboutMe')"
            >A propos</a
          >
        </li>
        <li>
          <a
            :class="{ active: activeSection === 'skills' }"
            @click.prevent="navigateAndScroll('skills')"
            >Compétences</a
          >
        </li>
        <li>
          <a
            :class="{ active: activeSection === 'projectDetail' }"
            @click.prevent="navigateAndScroll('projectDetail')"
            >Projets</a
          >
        </li>
        <li>
          <a
            :class="{ active: activeSection === 'contact' }"
            @click.prevent="navigateAndScroll('contact')"
            >Contact</a
          >
        </li>
      </ul>
    </nav>
  </header>
</template>

<script setup>
import { ref, nextTick } from "vue";
import { useRouter } from "vue-router";

const activeSection = ref(null);
const router = useRouter();

// navigateAndScroll permet de naviguer vers la page d'accueil grâce à router.push
// nextTick permet d'attendre le chargement de la page d'accueil avant de faire défiler vers la section correspondante
const navigateAndScroll = (sectionId) => {
  router.push("/").then(() => {
    nextTick(() => {
      scrollToSection(sectionId);
    });
  });
};

// scrollToSection permet de faire défiler la page vers la section correspondante
const scrollToSection = (sectionId) => {
  const section = document.getElementById(sectionId);
  if (section) {
    section.scrollIntoView({ behavior: "smooth" });
    activeSection.value = sectionId;
  }
};
</script>

<style scoped>
.header .menu_navBar a.active {
  text-decoration: underline;
  color: rgb(26, 112, 146);
}

.header {
  background-color: #ffffff;
  position: sticky;
  z-index: 100;
  top: 0;
  display: flex;
  justify-content: flex-start;
}

.navBar {
  margin-left: 11rem;
}

.header .logo {
  font-family: "Poppins", sans-serif;
  font-size: 1.5rem;
  font-weight: bold;
  padding-left: 70px;
}

.header li {
  list-style: none;
  display: inline-flex;
  align-items: center;
}

.header .menu_navBar li {
  padding: 0 1.5rem;
}

.header .logo:hover,
.header a:hover {
  cursor: pointer;
  color: rgb(26, 112, 146);
}

.header a.active {
  text-decoration: underline;
}

/*Adaptation de la barre de navigation pour les écrans de taille inférieure à 750px*/
@media screen and (max-width: 749px) {
  .navBar {
    margin-left: 0;
  }
  .header li {
    list-style: none;
    display: flex;
    flex-direction: column;
    align-items: flex-start;
  }
}
</style>
