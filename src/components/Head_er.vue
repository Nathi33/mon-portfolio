<template>
  <header class="header">
    <h2 class="logo">
      <a @click="scrollToSection('welcome')">Nath Drnt</a>
    </h2>

    <nav class="navBar">
      <ul class="menu_navBar">
        <li>
          <!--Permet de souligner lorsque l'élément du menu est  actif-->
          <a
            :class="{ active: activeSection === 'welcome' }"
            @click="scrollToSection('welcome')"
            >Accueil</a
          >
        </li>
        <li>
          <a
            :class="{ active: activeSection === 'aboutMe' }"
            @click="scrollToSection('aboutMe')"
            >A propos</a
          >
        </li>
        <li>
          <a
            :class="{ active: activeSection === 'skills' }"
            @click="scrollToSection('skills')"
            >Compétences</a
          >
        </li>
        <li>
          <a
            :class="{ active: activeSection === 'projectDetail' }"
            @click="scrollToSection('projectDetail')"
            >Projets</a
          >
        </li>
        <li>
          <a
            :class="{ active: activeSection === 'contact' }"
            @click="scrollToSection('contact')"
            >Contact</a
          >
        </li>
      </ul>
    </nav>

    <div class="social">
      <ul class="social_link">
        <li>
          <!--L'attribut "rel" sert à améliorer la  sécurité des liens externes en protégeant contre  certaines attaques-->
          <a
            target="_blank"
            href="https://facebook.com/"
            rel="noopener noreferrer"
            ><img src="../assets/images/facebook.png" alt="logo facebook"
          /></a>
        </li>
        <li>
          <a
            target="_blank"
            href="https://fr.linkedin.com/"
            rel="noopener noreferrer"
            ><img src="../assets/images/linkedin.png" alt="logo linkedin"
          /></a>
        </li>
        <li>
          <a
            target="_blank"
            href="https://twitter.com/?lang=fr"
            rel="noopener noreferrer"
            ><img src="../assets/images/twitter.png" alt="logo twitter"
          /></a>
        </li>
        <li>
          <a
            target="_blank"
            href="https://instagram.com/"
            rel="noopener noreferrer"
            ><img src="../assets/images/instagram.png" alt="logo instagram"
          /></a>
        </li>
      </ul>
    </div>
  </header>
</template>

<script setup>
import { ref } from "vue";

const activeSection = ref(null);

const scrollToSection = (sectionId) => {
  const section = document.getElementById(sectionId);
  if (section) {
    section.scrollIntoView({ behavior: "smooth" });
    activeSection.value = sectionId;
  }
};
</script>

<style scoped>
/*Essai*/
.header a.active {
  text-decoration: underline;
  color: rgb(26, 112, 146); /* Ajoutez la couleur souhaitée */
}
/*Fin Essai*/
.header {
  background-color: #ffffff;
  position: sticky;
  z-index: 100;
  top: 0;
  display: flex;
  justify-content: space-between;
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

.header .social_link {
  padding-right: 30px;
}

.header .menu_navBar li {
  padding: 0 1.5rem;
}

.header .social_link li {
  padding: 0 0.5rem;
}

.header .logo:hover,
.header a:hover {
  cursor: pointer;
  color: rgb(26, 112, 146);
}

.header a.active {
  text-decoration: underline;
}
.social_link img {
  width: 20px;
  height: 20px;
}

/*Adaptation de la barre de navigation pour les écrans de taille inférieure à 750px*/
@media screen and (max-width: 749px) {
  .header li {
    list-style: none;
    display: flex;
    flex-direction: column;
    align-items: flex-start;
  }
}
</style>
