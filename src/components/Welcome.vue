<template>
  <section id="welcome">
    <div class="hero">
      <div class="hero_left">
        <h1 class="title">Bienvenue sur mon Portfolio</h1>
        <h2 class="sentence">Nath Drnt, une jeune développeuse en herbe</h2>
      </div>

      <div class="hero_right">
        <div class="hero-img">
          <img src="../assets/images/avatar.png" alt="Avatar Nath" />
        </div>
      </div>
    </div>
  </section>
</template>

<script setup></script>

<style scoped>
.hero {
  background-color: rgba(182, 121, 182, 0.849);
  display: flex;
  flex-direction: column; /* Affichage en colonne par défaut, changement en fonction de la largeur de l'écran */
  align-items: center;
  padding: 5%;
}

.hero .title {
  font-size: 2.5rem;
  text-shadow: 2px 2px 4px white;
  font-weight: bold;
  line-height: 1.5;
  text-align: start;
  margin-top: 1rem; /* Espacement du titre par rapport au span */
}

.hero .sentence {
  font-weight: normal;
  font-size: 1.5rem;
  text-align: start;
  margin-top: 5rem; /* Espacement de la phrase par rapport au titre */
}

.hero_left {
  animation-duration: 1s;
  animation-name: slideInLeft;
  padding: 0; /* Suppression du padding à gauche */
}

.hero_right {
  animation-duration: 1s;
  animation-name: slideInRight;
  margin-top: 2rem; /* Espacement du bloc droit par rapport au bloc gauche */
}

.hero-img img {
  width: 100%; /* Utilisation de la largeur maximale */
  max-width: 400px; /* Largeur maximale pour les écrans plus larges */
  height: auto;
  border-radius: 50%;
  background-color: white;
}

/* Effet d'animation */
@keyframes slideInLeft {
  from {
    transform: translateX(-110%);
  }
  to {
    transform: translateX(0%);
  }
}

@keyframes slideInRight {
  from {
    transform: translateX(110%);
  }
  to {
    transform: translateX(0%);
  }
}

/* Ajustement pour grand écran */
@media screen and (min-width: 750px) {
  .hero {
    flex-direction: row;
    justify-content: space-around;
  }

  .hero-img img {
    width: 400px;
    height: 400px;
  }
}

/* Ajustement pour petit écran */
@media screen and (max-width: 750px) {
  .hero {
    flex-direction: column-reverse; /* Inversion de la direction pour les petits écrans */
    align-items: center; /* Centrage des éléments */
  }

  .hero_right {
    margin-top: 3rem; /* Ajuste la marge entre le bloc droit et le bloc gauche */
  }

  .hero-img img {
    max-width: 100%;
    height: auto;
    border-radius: 50%;
    margin-bottom: 1.5rem; /* Ajoute de l'espace entre l'avatar et le texte */
  }
}
</style>
