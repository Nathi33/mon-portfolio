<template>
  <section id="aboutMe">
    <div class="aboutme">
      <figure class="aboutme_img">
        <img
          src="../assets/images/photo.jpg"
          alt="Portrait de Nath Drnt, développeur web et mobile"
        />
      </figure>
      <div class="aboutme_description">
        <div class="description">
          <h2>A propos</h2>
          <p>
            Après de nombreuses années dans le secteur du paramédical et du
            secrétariat, j'ai décidé de donner un nouveau souffle à ma carrière
            et de me lancer dans l'aventure du "Développement Web".<br />
            J'ai commencé par suivre des formations dispensées sur internet via
            OpenCLassRooms ou encore Le Réacteur afin de m'initier au code.
            Cette première approche m'a permis de me conforter dans l'idée de
            faire du Développement ma nouvelle vocation. J'ai donc débuté ma
            formation de Développeur Web et Mobile au sein du Centre Européen de
            Formation. Depuis, je code quotidiennement avec chaque jour
            davantage de passion.<br />Si je ne suis encore que "junior" en
            développement, mon parcours professionnel m'a appris le travail en
            équipe, l'adaptation, la rigueur et l'écoute des besoins du
            client.<br />J'espère pouvoir mettre mon enthousiasme, mes
            compétences et ma créativité à votre disposition.
          </p>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup></script>

<style scoped>
.description h2 {
  font-size: 2.5rem;
}

.aboutme {
  padding-top: 3%;
  padding-bottom: 5%;
  display: flex;
  flex-direction: column; /* Affichage en colonne par défaut, changement en fonction de la largeur de l'écran */
  align-items: center;
}

.aboutme_img img {
  display: flex;
  align-items: center;
  object-fit: contain;
  max-width: 100%;
  height: auto;
  margin-bottom: 2%;
}

.aboutme_description {
  text-align: justify;
  padding: 2%;
}

.description {
  display: flex;
  flex-direction: column; /* Alignement en colonne pour les petits écrans */
  align-items: center;
}

/* Ajustement pour grand écran */
@media screen and (min-width: 768px) {
  .aboutme {
    flex-direction: row; /* Affichage en ligne pour les écrans plus larges */
  }

  .aboutme_img {
    margin-right: 4%; /* Espacement entre l'image et le texte */
  }

  .description {
    align-items: flex-start; /* Alignement à gauche pour les grands écrans */
  }
}
</style>
