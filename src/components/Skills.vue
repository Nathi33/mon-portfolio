<template>
  <main class="my_skills">
    <section id="skills">
      <div class="skills">
        <h2>Compétences</h2>
        <div class="skills_description">
          <figure class="technique">
            <h3>Compétences techniques</h3>
            <img src="../assets/images/Logos.jpg" alt="logos compétences" />
          </figure>
          <div class="transverse">
            <h3>Compétences transversales</h3>
            <ul>
              <li>Autonomie</li>
              <li>Rigueur et efficacité</li>
              <li>Aisance relationnelle</li>
              <li>Ecoute et adaptabilité</li>
              <li>Travail en équipe</li>
            </ul>
          </div>
        </div>
      </div>
    </section>
  </main>
</template>

<script setup></script>

<style scoped>
.skills h2 {
  font-size: 2.5rem;
  text-align: center;
  padding-bottom: 1.5rem;
}

.skills {
  padding: 40px 20px 60px;
  background-color: rgba(182, 121, 182, 0.849);
}

.skills_description {
  display: flex;
  flex-direction: column; /*Affichage en colonne par défaut, changement en fonction de la largeur de l'écran */
  align-items: stretch;
  justify-content: space-around;
  height: 100%;
}

.technique,
.transverse {
  border: solid black 1px;
  background-color: aliceblue;
  margin-bottom: 20px;
  padding: 20px;
  display: flex;
  flex-direction: column; /* Affichage en colonne par défaut, changement en fonction de la largeur de l'écran */
  align-items: center;
}

.transverse {
  margin-top: 16px;
}

.technique img {
  width: 100%;
  max-width: 200px;
  height: auto;
}

.transverse ul {
  list-style-type: none;
  padding: 0;
  margin: 0;
}

.transverse li {
  line-height: 2.5;
}

/* Ajustement des styles pour grand écran */
@media screen and (min-width: 768px) {
  .skills_description {
    flex-direction: row; /* Affichage en ligne pour les écrans plus larges */
  }

  .technique,
  .transverse {
    flex: 1; /* Partager l'espace disponible de manière égale entre les deux éléments */
  }

  .transverse {
    margin-left: 20px; /* Espacement entre les deux éléments */
  }
}

/* Ajustement des styles pour petit écran */
@media screen and (max-width: 750px) {
  h3 {
    font-size: 1.3rem;
  }
}
</style>
